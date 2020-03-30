# string data generation
### 用法

在数据生成器前面加上 `#include "gen_string.h"`

### 类

`char_set`（字符集）：

​	`init`：初始化。

​	`add_ch(c)`：增加字符 c。

​	`add_chs(l,r)`：增加从 l 到 r 的字符。

​	`add_upper_case()`：初始化为大写字母。

​	`add_lower_case()`：初始化为小写字母。

​	`add_numbers()`：初始化为数字。

​	`gen_char()`：从字符集里面随机抽取一个字符。

### 函数

`rand_int()`：生成随机 `int` 范围内整数。

`random(l,r)`：生成 [l,r]​ 内整数。

`gen_rand_string(len,c)`：用字符集 c 生成长度为 len 的随机字符串。

`gen_palindrome(len,c)`：用字符集 c 生成长度为 len 的随机回文字符串。

`add_noise(s,c,cnt)`：用字符集 c 为 s 添加 cnt 个噪音，也就是随机 cnt 个位置，放上随机字符。

`repeat(pattern,cnt)`：将 pattern 这个字符串重复 cnt 次，生成新的字符串。

### 举例

```cpp
cout<<add_noise(repeat("poiop",2000),rnd,10); //生成一个由 poiop 重复 2000 次形成的字符串，添加 10 点噪音

char_set c;
c.init();
c.add_ch('a');
c.add_ch('b');
cout<<gen_rand_string(n,c); //生成一个随机的由 a,b 构成的长度为 n 的字符串
cout<<gen_palindrome(n,c); //生成一个随机的由 a,b 构成的长度为 n 的回文串

c.init();
c.add_lower_case();
cout<<gen_rand_string(n,c); //生成一个随机的由小写字母构成的长度为 n 的字符串
```

