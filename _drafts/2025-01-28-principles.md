---
layout: post
title: Principles
date: 2025-01-28 16:15 +0200
---

## What is it?
A principle is a truth, a fundamental way of life. One can think of a principle as the implementation of "because I said so". Google neatly adds to the definition by stating that it's the truth used as a foundation for a behavior or reason. 

Many of us have principles we are vastly unawre of, but I want to share some of my own insights in some coding principles. I only recently (yesterday as of writing) discovered that I am extremely biased into a very specific principle.

## Different Principles
We will focus specifally on:
- LoB: Locality of Behavior
- DRY: Don't Repeat Yourself
- SoC: Separation of Concerns

### 1. Locality of Behavior
Our first principle states that a unit of code must be obvious from only looking at this unit of code. The "formal" definition, although vague, is just that. It is the principle that what I'm working on should be right here. To expand or perhaps start our understanding of this let's look at an example:

```groovy
// File: People.groovy

String SQL = "SELECT id, name, surname FROM people WHERE people.name = 'Liam';"

NativeQuery q = session.createNativeQuery(SQL)
q.executeUpdate()
```

From this the principle isn't immediatly obvious, but allow me to show another example which **does not** satisfy the principle:

```sql
-- File: PeopleQuery.sql

SELECT id, name, surname FROM people WHERE people.name = 'Liam';
```

```groovy
// File: People.groovy

String sql = new File('/path/to/PeopleQuery.sql').text

NativeQuery q = session.createNativeQuery(sql)
q.executeUpdate()
```

Can you see the difference? If not, do not fear, I shall explain. The first utilizes the fact that the SQL statement is written right then and there. There is no other location for the SQL although it might change. The second separates the two into different files. They are coupled through code.

### 2. Don't Repeat Yourself
"Staying DRY" sadly doesn't mean avoiding the deep seas, but rather that you should avoid redudancy. The wheel is already invented, the developer must simply change its size, the rim, the shape, the usecase, the color, the threading, the material, the spikes, and a few other override-able properties! I'm just kidding, there is truly no need to re-invent everything. A developer must strive to always remove redudancy as often as machinely possible! Below a wet and dry example:

```go

slice := [1,2,3,4,5]
shuffledSlice := slice.copy()

r := rand.New(rand.NewSource(time.Now().UnixNano()))
r.Shuffle(len(shuffledSlice), func(i, j int) {
    shuffledSlice[i], shuffledSlice[j] = shuffledSlice[j], shuffledSlice[i]
})

var shuffledTwiceSlice := shuffledSlice.copy()
r.Shuffle(len(shuffledSlice), func(i, j int) {
    shuffledSlice[i], shuffledSlice[j] = shuffledSlice[j], shuffledSlice[i]
})
```

```go

func ShuffleSlice(a []int) []int {
	r := rand.New(rand.NewSource(time.Now().UnixNano()))
	r.Shuffle(len(a), func(i, j int) {
		a[i], a[j] = a[j], a[i]
	})

	return a
}

slice := [1,2,3,4,5]
shuffledSlice := ShuffleSlice(slice)
shuffledTwiceSlice := ShuffleSlice(shuffledSlice)
```

A clear difference between the two! Both will achieve the same, however the second is much more clear and the `shuffleSlice` function can be used anywhere else it will be required.

## 3. Separation of Concerns