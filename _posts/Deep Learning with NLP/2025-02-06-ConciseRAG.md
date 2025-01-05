---
title: Concise RAG
tags: RAG deep-learning NLP
katex: True
layout: post
subtitle: How to Efficiently Find Binomial Coefficients of Large Numbers
image: /images/thumbnails/Learn ML.png
category: Deep Learning with NLP
---

# 0. Introduction and Prerequisites

The article gives concise details of RAG system.

Prerequisites: Deep learning based language models (basic understanding)

RAG stands for Retrieval Augemented Generation. 

TODO: Write from here on.

This [Article](https://fishi.devtail.io/weblog/2015/06/25/computing-large-binomial-coefficients-modulo-prime-non-prime/) with link.

이 In this article, I'll explain what I learned in high school about how to find the binomial coefficient, and especially how to deal with it when the numbers grow and I run out of time in the usual way.

# Main text

Write md file $$\binom{N}{K} = \frac{N!M!}{(N-K)!} (0\le k\le n)$$ 


# 1. some section

Write here

## subsection

$$(a+b)\mod m = (a\mod m) + (b\mod m)\mod m$$ 

**Code : Calculate pascal's triangle**

```python
#!/usr/bin/env python3

"""
Calculate Pascal's Triangle to Calculate the Binomial Coefficient nCk % m
"""

# Calculating Pascal's Triangle until row 'n' with modulo 'mod'
# Write some comment
# Time Complexity:	O(n**2)
# Space Complexity:	O(n**2)

def pascal_triangle(n,mod):
    # prepare first row in table
    pascal = []
    pascal.append([1,0])

    for i in range(1,n+1):
        pascal.append([])
        pascal[i] = [0]*(i+2)
        pascal[i][0] = 1

        for j in range(1,i+1):
            pascal[i][j] = (pascal[i-1][j] + pascal[i-1][j-1])%mod

    return pascal

if __name__ == '__main__':
    n = 1009 # number of rows in pascal table
    mod = 123456 # 소수가 아님

    # mod 123456 이 적용된 파스칼의 삼각형 계산하기
    pascal = pascal_triangle(n,mod)

    # (950 C 100) mod 123456
    print(pascal[950][100]) # 정답은 24942가 될것
```

Write some things here

**Code : For all m callculte pascal's triangle**

```python
#!/usr/bin/env python3

"""
Calculating a row in Pascal's Triangle to determine Binomial Coefficients
"""


# Time Complexity:	O(n**2)
# Space Complexity:	O(n)
def pascal_triangle_row(n,mod):
    pascal = [0]*(n+1)
    pascal[0] = 1

    for i in range(1,n+1):
        tmp = [0]*(n+1)
        tmp[0] = 1

        for j in range(1,i+1):
            tmp[j] = (pascal[j] + pascal[j-1])%mod

        pascal = tmp

    return pascal

if __name__ == '__main__':
    n = 950 # row of pascal table
    mod = 123456 # not a prime

    pascal_row = pascal_triangle_row(n,mod)

    # (950 C 100) mod 123456
    print(pascal_row[100]) # 정답은 24942 일것
```

Write some things here

# 2. Section 2

Write

## subsection

write

# Section 3

End.
