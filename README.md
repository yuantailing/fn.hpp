# fn.hpp [draft]
A funny way to write lambda-like expressions.

This project is inspired by [fn.py](https://github.com/kachayev/fn.py).

## Usage

```cpp
#include <iostream>   // std::cout, std::endl
#include <algorithm>  // std::count_if, std::sort
#include "fn.hpp"     // fn::_

using namespace std;
using namespace fn;

int main() {
  auto add = _ + _;
  cout << add(1, 2) << endl;
  // Expected: 3

  int a[5] = {5, 6, 7, 8, 9};
  cout << count_if(a, a + 5, _ % 2 == 0) << endl;
  // Expected: 2

  sort(a, a + 5, _ > _);
  for (auto x: a)
    cout << x << " ";
  cout << endl;
  // Expected: 9 8 7 6 5

  auto foo = _1[0] + _1[2] + _1[4];
  cout << foo(a) << endl;
  // Expected: 21

  return 0;
}
```
