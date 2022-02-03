# assignment2-Bush
WebApps Markdown Practice 
# Drake Bush
## Senor Burrito
Senor Burrito sits across the street from a **US Bank** Branch. **Citizens Bank & Trust** is north on main from Senor Burrito. Behind Senor Burrito, to its east, lies **First Baptist Church**.


***

# Directions from NW Missouri Reigonal Airport to Senor Burrito
1. Take a right when exiting the airport 
2. Take a left on 46 highway and travel for about 4 Miles
3. Take a right on main street
4. The destination will be on youur left

Things you MUST try
* Nachos
* Carnitas
* Barbacoa 
* Burrito
* Jarritos

Learn More about me [Here](https://github.com/dtbush/assignment2-Bush/edit/main/ABOUTME.md)

***

# Sports
|Sport|Location|Equipment Price|
| --- | ---     | --- |
|Football|Bearcat Stadium|$750|
|Soccer| Field House| $150 |
|Basketball| Bearcat Arena| $150|

***

# Quotes
> "We cannot solve our problems with the same thinking we used when we created them." -*Albert Einstein*

> "The first step is to establish that something is possible; then probability will occur." -*Elon Musk*

***

# Algoritm
> A Fenwick tree or binary indexed tree is a data structure that can efficiently update elements and calculate prefix sums in a table of numbers -[Source](https://en.wikipedia.org/wiki/Fenwick_tree)

```
struct FenwickTree {
    vector<int> bit;  // binary indexed tree
    int n;

    FenwickTree(int n) {
        this->n = n;
        bit.assign(n, 0);
    }

    FenwickTree(vector<int> a) : FenwickTree(a.size()) {
        for (size_t i = 0; i < a.size(); i++)
            add(i, a[i]);
    }

    int sum(int r) {
        int ret = 0;
        for (; r >= 0; r = (r & (r + 1)) - 1)
            ret += bit[r];
        return ret;
    }

    int sum(int l, int r) {
        return sum(r) - sum(l - 1);
    }

    void add(int idx, int delta) {
        for (; idx < n; idx = idx | (idx + 1))
            bit[idx] += delta;
    }
};
```
[Code Source](https://cp-algorithms.com/data_structures/fenwick.html)
