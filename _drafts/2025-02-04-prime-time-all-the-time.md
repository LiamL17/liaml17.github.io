---
layout: post
title: Prime Time All The Time
date: 2025-02-04 15:57 +0200
---

## Prime numbers
A prime number is a number divisable by 1 and itself. That's it! There's nothing more to it. There might be if you want it to be, but that's the basic of prime numbers. "How come people often talk about them", the simpleton asks. Fear not, allow the **intellectual** to answer.  

![Mr Bean Waiting](/assets/img/posts/mr-bean-waiting.gif)

It seems the **intellectual** did not respond. Allow me to take a stab at it.

But all of that yapping is simply to get to the actual content of the post. I want to see in how many programming languages can I write an `isPrime` function! With that knowledge, welcome to the abyss as we dive into all sorts of programming languages trying to discover a prime!

## Table Of Contents

| Language |
|-------|
| [Java](#java) |
| [Groovy](#groovy) |
| [Kotlin](#kotlin) |

### Java
```java
boolean isPrime(int n) {
    if (n < 2) return false;
    for (int i = 2; i * i <= n; i++) {
        if (n % i == 0) return false;
    }
    return true;
}
```

### Groovy

### Kotlin