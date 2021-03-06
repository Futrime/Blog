---
title: 如何遵循Apache 2.0协议
date: 2020-05-03 18:26:00
draft: false
author: Futrime
image: https://futrime.gitee.io/image-cdn/2020/03/760153492.jpg
description: 这篇文章我就简单讲一下如何遵循Apache 2.0协议。
categories:
  - 经验杂谈
tags:
  - Apache 2.0
  - 开源协议
  - OSI
  - ASF
---


最近在写代码的过程中需要引用一些代码，而被引用的仓库提示遵循Apahce-2.0协议。我在搜索引擎查找了很久都没能够找到具体方法。或许这对于开源领域的熟手来说并不算什么，但是对于像我这样刚踏入开源领域的蒟蒻来说就成了莫大的障碍。终于我在StackOverflow和SlackExchange上找到了遵循方法。这篇文章我就简单讲一下如何遵循Apache 2.0协议。

首先在ASF官网找到Apache 2.0的原文如下：

![Screenshot_2020-03-22 Apache License, Version 2 0.png][2]

直接拉到 `4. Redistribution`，这里才是我们真正关注的地方：

![Screenshot_2020-03-22 Apache License, Version 2 0(1).png][3]

先说说官方的声明如下：

```
Copyright [yyyy] [Name]

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```

官方承认的的简化版本如下：

```
Copyright [yyyy] [name of copyright owner]
SPDX-License-Identifier: Apache-2.0
```

这个版本我们也是可以用的，尤其在代码量少的时候比较好用。

先看第一条：

```
    You must give any other recipients of the Work or Derivative Works a copy of this License; and
```

这条要求我们在仓库中保留一份`LICENSE`文件。如果我们自己的项目本身就是遵循Apache 2.0协议的话，就不需要改动，直接保留自己的`LICENSE`文件。如果我们自己的项目本身不是Apache 2.0协议，那么原则上就需要保留一份Apache 2.0协议副本。**但是！根据我观察众多著名仓库的结果发现，其实不需要这么做，只需要我们在引用的文件中保留原作者的声明（如果原作者声明用了简化版本，那么需要附加上链接`http://www.apache.org/licenses/LICENSE-2.0`。

再看第二条：

```
    You must cause any modified files to carry prominent notices stating that You changed the files; and
```

这条就是说需要我们在修改了的文件上加上自己的声明。一般来说就是在自己修改的代码段前面加上官方声明，其中第一行改为：
```
Modifications Copyright [时间] [你的名字]
```

其实这和第二条异曲同工：

```
    You must retain, in the Source form of any Derivative Works that You distribute, all copyright, patent, trademark, and attribution notices from the Source form of the Work, excluding those notices that do not pertain to any part of the Derivative Works; and
```

第二条是指保留自己声明，第三条指保留原作者声明。如果只是引用一个代码段，那么就在这个代码段之前加入声明即可。

最后看看第四条：

```
    If the Work includes a "NOTICE" text file as part of its distribution, then any Derivative Works that You distribute must include a readable copy of the attribution notices contained within such NOTICE file, excluding those notices that do not pertain to any part of the Derivative Works, in at least one of the following places: within a NOTICE text file distributed as part of the Derivative Works; within the Source form or documentation, if provided along with the Derivative Works; or, within a display generated by the Derivative Works, if and wherever such third-party notices normally appear. The contents of the NOTICE file are for informational purposes only and do not modify the License. You may add Your own attribution notices within Derivative Works that You distribute, alongside or as an addendum to the NOTICE text from the Work, provided that such additional attribution notices cannot be construed as modifying the License.

    You may add Your own copyright statement to Your modifications and may provide additional or different license terms and conditions for use, reproduction, or distribution of Your modifications, or for any such Derivative Works as a whole, provided Your use, reproduction, and distribution of the Work otherwise complies with the conditions stated in this License.
```

就是说我们要在`NOTICE`中写明用了谁的代码，以及哪些文件修改了。

参考链接：
1. https://www.apache.org/licenses/LICENSE-2.0
1. https://www.apache.org/foundation/license-faq.html
1. https://opensource.org/licenses/Apache-2.0

  [2]: https://futrime.gitee.io/image-cdn/2020/03/222458797.png
  [3]: https://futrime.gitee.io/image-cdn/2020/03/1550260874.png
