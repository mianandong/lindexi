---
layout: post
title:  win10 uwp ping 
category: uwp 
stickie: False
---

有时需要进行 ping ，但是ms没有给一个类可以进行 ping

本文：如何使用 ping

<!--more-->

<!-- csdn -->

不管什么，大概没有人还不知道什么是 ping，如果不知道的话，请百度一下，虽然百度很垃圾，不过找这个还是很简单。

简单的方法是使用大神写的

打开 Nuget ，搜索 System.Net.Ping ，接下来就是很简单

第二个方法是使用下面代码，注意把他放在一个函数，这里测试的是 lindexi.oschina.io


```csharp
               HostName host = new HostName("lindexi.oschina.io");
            var eps = await DatagramSocket.GetEndpointPairsAsync(host , "80");
            if(eps.Count >= 1)
            {
                return true;
            }
            else
            {
                return false;
            }
```


参见：http://stackoverflow.com/questions/37300532/ping-class-not-available-in-uwp

![](http://7xqpl8.com1.z0.glb.clouddn.com/34fdad35-5dfe-a75b-2b4b-8c5e313038e2%2F201792392937.jpg)

 