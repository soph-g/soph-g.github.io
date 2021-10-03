---
layout: post
title: "001 - Double Trouble 👯‍♀️"
date: 2021-10-03 17:05:00 +0000
excerpt_separator: <!--more-->
categories: [learning, habits, daily kata, numbers, linked lists, stacks]
published: true
---

I spent a lot of time doing katas at the start of the year but have let the practice drop as life got a bit hectic.

I sat down today to do some practice katas for an interview prep group, and thought I'd share the outcome here.

I covered two problems today:

- [Persistence](https://www.codewars.com/kata/55bf01e5a717a0d57e0000ec/train/ruby)

- [Reverse Linked List](https://leetcode.com/problems/reverse-linked-list/)

<!--more-->
## Problem 1 - Persistence

[Link to the codewars problem](https://www.codewars.com/kata/55bf01e5a717a0d57e0000ec/train/ruby)

First attempt:

```ruby
def persistence(n, count = 0)
  return count if n < 10

  persistence(n.to_s.split('').map(&:to_i).reduce(:*), count + 1)
end
```

This was my first attempt. In this approach I decided to access the individual digits in the integer by turning it into a string, then splitting that string into an array, then mapping over the array to turn the strings back into integers, before using `reduce` to calculate the product of the individual digits.

This solution also uses recursion to continually split and calculate the product until a single digit number is reached. While this solution works, it's not optimal, and transforming the integer into a string felt a bit off.

I then remembered that we can use `n % 10` to return only the last digit of a number, so decided to utilise this approach in my refactored code:

```ruby
def persistence(n, count = 0)
  return count if n < 10

  total = 1

  while n > 0 do
    total *= n % 10
    n = n / 10
  end

  persistence(total, count + 1)
end
```

While this code looks longer, it's actually performing fewer operations on `n` so will be more performant.

## Problem 2 - Reverse a linked list

[Link to the LeetCode problem](https://leetcode.com/problems/reverse-linked-list/)

I was very rusty on this, but I did remember that stacks are generally quite handy when trying to reverse the order of something. Ruby doesn't have a stack object, so I used an array for the same purpose.

```ruby
def reverse_list(head)
  stack = []
  node = head

  while node&.next do
    stack << node
    next_node = node.next
    node.next = nil
    node = next_node
  end

  reversed_head = node

  while stack.any? do
    node.next = stack.pop
    node = node.next
  end

  reversed_head
end
```

I initially ran into some problems here because I forgot to remove the original links in the link list, which was creating an infinite loop when I tried to rebuild the list in reverse order. Once I'd spotted the problem it was a simple case of setting `node.next` to `nil` when pushing nodes onto the stack.

I could probably improve both of these solutions, but today wasn't about writing optimal code, it was about getting back into the problem solving mindset.
