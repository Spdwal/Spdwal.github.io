---
layout: post
title: "CodeWar from zero to one Arithmetic progression"
category: 
tags: []
---

#  Arithmetic progression

In your class, you have started lessons about [arithmetic progression](https://en.wikipedia.org/wiki/Arithmetic_progression). Since you are also a programmer, you have decided to write a function that will return the first `n` elements of the sequence with the given common difference `d` and first element `a`. Note that the difference may be zero!

The result should be a string of numbers, separated by comma and space.

## Example

```python
# first element: 1, difference: 2, how many: 5
arithmetic_sequence_elements(1, 2, 5) == "1, 3, 5, 7, 9"
```



```c++
#include <string>


std::string arithmeticSequenceElements(int a, int r, int n)
{
    std::string ret;
    while(n != 0){
        ret += std::to_string(a);
        a += r;
        n--;
        if(n != 0){
            ret += std::string(", ");
        }
    }
    return ret;
}
```

