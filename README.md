# fn.hpp [withdrew]
A funny way to write lambda-like expressions.

This project is inspired by [fn.py](https://github.com/kachayev/fn.py).

## Usage

```cpp
#include <iostream>   // std::cout, std::endl
#include <string>     // std::string
#include <vector>     // std::vector
#include <algorithm>  // std::count_if, std::sort
#include "fn.hpp"     // fn::_

using namespace std;
using namespace fn;

int main() {
  auto add = _ + _;
  cout << add(1, 2) << endl;
  // Expected: 3

  cout << add(string("Hello"), " World!") << endl;
  // Expected: Hello World!

  vector<int> a = {5, 6, 7, 8, 9};
  cout << count_if(a.begin(), a.end(), _ % 2 == 0) << endl;
  // Expected: 2

  sort(a.begin(), a.end(), _ > _);
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

## Withdrew

I rack my brain and discussed with friends but cannot implement it now.
