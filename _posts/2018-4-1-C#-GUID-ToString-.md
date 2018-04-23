---
title: "C# GUID ToString "
author: lindexi
date: 2018-4-1 10:41:3 +0800
CreateTime: 2018-4-1 10:16:6 +0800
categories: C#
---

最近在看到小伙伴直接使用 Guid.ToString ，我告诉他需要使用 Guid.ToString("N") ，为什么需要使用 N ，因为默认的是 D 会出现连字符。

<!--more-->


<!-- csdn -->

Guid 是 Globally Unique Identifier 全局唯一标识符，是一种由算法生成的唯一标识是微软的UUID标准的实现。

Guid.ToString 里面可以添加下面几个参数，“N”，“D”，“B”，“P”，“X”

如果直接使用 `Guid.ToString()` 那么就是使用 “D”，这个值大概就是在数字中添加连字符

```csharp
00000000-0000-0000-0000-000000000000
536b4dd7-f3dd-4664-bd69-bc0859d710ab
```

如果使用 “N” 那么就是只有32位数字，数字是 16 进制，字符串有 a-f

```csharp
00000000000000000000000000000000
2329fcac4fd640f1bc221e254b14d621
```

所以我就建议使用 N ，剩下的 B 和 P 只是在使用括号包字符串

```csharp
            System.Console.WriteLine(Guid.NewGuid().ToString("B"));
            {e34dead4-212d-442a-8f4c-e00107baec24}
```

```csharp
System.Console.WriteLine(Guid.NewGuid().ToString("P"));
(ac10d607-2b39-448f-99b5-0a3205cc9ac1)
```

从代码可以看到 B 使用`{` ，P 使用`(`，但是最特殊的是 x ，他会存在 4 个数字，最后一个数字是 8 个数字组合的

```csharp
   Console.WriteLine(Guid.NewGuid().ToString("X"));
  {0xd3f51d9d,0x31b3,0x45f6,{0x9b,0x7c,0x89,0x1d,0xa5,0x6a,0xa3,0x43}}
```

参见：[全局唯一标识符 - 维基百科，自由的百科全书](https://zh.wikipedia.org/wiki/%E5%85%A8%E5%B1%80%E5%94%AF%E4%B8%80%E6%A0%87%E8%AF%86%E7%AC%A6 )

![](http://7xqpl8.com1.z0.glb.clouddn.com/65fb6078-c169-4ce3-cdd9-e35752d07be0%2Fyande.re%2520443795%2520sample%2520bikini%2520goto_jun%2520kaneshiro_sora%2520momijidani_nozomi%2520noguchi_takayuki%2520swimsuits%2520tenshi_no_three_piece%2521201841104040.jpg)
