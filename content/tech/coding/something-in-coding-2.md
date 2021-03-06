+++
Description = "字符编码详解"
Tags = ["字符编码"]
date = "2011-08-14T17:21:26+08:00"
ds_title = "字符编码详解 part1"
title = "字符编码详解 part1"

+++
转自<a href="http://polaris.blog.51cto.com/1146394/377468">http://polaris.blog.51cto.com/1146394/377468</a>
编码系列1：<a href="http://sqh.me/blog/?p=263">编码那点事----历史进化</a>
编码系列2：<a href="http://sqh.me/blog/?p=273">字符编码详解 part1</a>
编码系列3：<a href="http://sqh.me/blog/?p=275">字符编码详解 part2</a>


每一个程序员都不可避免的遇到字符编码的问题，特别是做Web开发的程序员，“乱码问题”一直是让人头疼的问题，也许您已经很少遇到“乱码”问题，然而，对解决乱码的方法的内在原理，您是否明白？本人作为一个程序员，在字符编码方面同样遇到不少问题，而且一直对各种编码懵懵懂懂、不清不楚；在工作中也曾经遇到一个很烦人的编码问题。这两天在网上收集了大量编码方面的资料，对字符编码算是理解的比较清楚了。下面把我认为比较重要的知识点记录下来，一方面方便以后复习；另一方面也希望给跟我一样懵懵懂懂的人一个参考。不对或不妥之处，请批评指正。
<div>在此之前，先了解一些有用概念：“字符集”、“字符编码”和“内码”。</div>
<h2><strong>1、字符集与字符编码</strong></h2>
<div>字符是各种文字和符号的总称，包括各个国家文字、标点符号、图形符号、数字等。字符集是多个字符的集合，字符集种类较多，每个字符集包含的字符个数不同，常见字符集有：ASCII字符集、ISO 8859字符集、GB2312字符集、BIG5字符集、GB18030字符集、Unicode字符集等。计算机要准确的处理各种字符集文字，需要进行字符编码，以便计算机能够识别和存储各种文字。</div>
<div>编码(encoding)和字符集不同。字符集只是字符的集合，不一定适合作网络传送、处理，有时须经编码(encode)后才能应用。如Unicode可依不同需要以UTF-8、UTF-16、UTF-32等方式编码。</div>
<div>字符编码就是以二进制的数字来对应字符集的字符。</div>
<div>因此，对字符进行编码，是信息交流的技术基础。</div>
<div>使用哪些字符。也就是说哪些汉字，字母和符号会被收入标准中。所包含“字符”的集合就叫做“字符集”。</div>
<div>规定每个“字符”分别用一个字节还是多个字节存储，用哪些字节来存储，这个规定就叫做“编码”。</div>
<div>各个国家和地区在制定编码标准的时候，“字符的集合”和“编码”一般都是同时制定的。因此，平常我们所说的“字符集”，比如：GB2312, GBK, JIS 等，除了有“字符的集合”这层含义外，同时也包含了“编码”的含义。</div>
<div>注意：Unicode字符集有多种编码方式，如UTF-8、UTF-16等；ASCII只有一种；大多数MBCS（包括GB2312）也只有一种。</div>
<h2>2、什么是内码？</h2>
<div><strong>2.1 维基百科的解释</strong></div>
<div>在计算机科学及相关领域当中，内码指的是“将资讯编码后，透过某种方式储存在特定记忆装置时，装置内部的编码形式”。在不同的系统中，会有不同的内码。</div>
<div>在以往的英文系统中，内码为ASCII。在繁体中文系统中，目前常用的内码为大五码（Big5）。在简体中文系统中，内码则为国标码（国家标准代码：现在强制要求使用GB18030标准；较旧计算机仍然使用GB2312）。而统一码（Unicode）则为另一常见内码。</div>
<div><strong>2.2 百度百科的解释</strong></div>
<div>内码是指整机系统中使用的二进制字符编码，是沟通输入、输出与系统平台之间的交换码，通过内码可以达到通用和高效率传输文本的目的。比如MS Word中所存储和调用的就是内码而非图形文字。英文ASCII字符采用一个字节的内码表示，中文字符如国标字符集中，GB2312、GB12345、GB13000皆用双字节内码，GB18030（27,533汉字）双字节内码汉字为20,902个，其余6,631个汉字用四字节内码。</div>
<h2>3、字符编码分类总结</h2>
<div>下面从计算机对多国语言支持的角度来总结字符编码。</div>
<div><strong>3.1 ASCII编码</strong></div>
<div>以下来自“维基百科”：</div>
<div>ASCII（American Standard Code for Information Interchange，美国信息互换标准代码）是基于拉丁字母的一套电脑编码系统。它主要用于显示现代英语，而其扩展版本EASCII则可以勉强显示其他西欧语言。它是现今最通用的单字节编码系统（但是有被UniCode追上的迹象），并等同于国际标准ISO/IEC 646。</div>
<div>ASCII第一次以规范标准的型态发表是在1967年，最后一次更新则是在1986年，至今为止共定义了128个字符；其中33个字符无法显示（这是以现今操作系统为依归，但在DOS模式下可显示出一些诸如笑脸、扑克牌花式等8-bit符号），且这33个字符多数都已是陈废的控制字符。控制字符的用途主要是用来操控已经处理过的文字。在33个字符之外的是95个可显示的字符，包含用键盘敲下空白键所产生的空白字符也算1个可显示字符（显示为空白）。</div>
<div>ASCII表：见http://zh.wikipedia.org/zh-cn/ASCII</div>
<div>ASCII缺点：</div>
<div>ASCII的最大缺点是只能显示26个基本拉丁字母、阿拉伯数目字和英式标点符号，因此只能用于显示现代美国英语（而且在处理英语当中的外来词如naïve、café、élite等等时，所有重音符号都不得不去掉，即使这样做会违反拼写规则）。而EASCII虽然解决了部份西欧语言的显示问题，但对更多其他语言依然无能为力。因此现在的苹果电脑已经抛弃ASCII而转用Unicode。</div>
<div>最早的英文DOS操作系统的系统内码是：ASCII。计算机这时候只支持英语，其他语言不能够在计算机存储和显示。</div>
<div>在该阶段，单字节字符串使用一个字节存放一个字符（SBCS,Single Byte Character System）。如："Bob123"占6个字节。</div>
<div><strong>3.2 ANSI编码</strong></div>
<div>为使计算机支持更多语言，通常使用0x800~xFF范围的2个字节来表示1个字符。比如：汉字 '中' 在中文操作系统中，使用 [0xD6,0xD0]这两个字节存储。</div>
<div>不同的国家和地区制定了不同的标准，由此产生了GB2312,BIG5,JIS等各自的编码标准。这些使用2个字节来代表一个字符的各种汉字延伸编码方式，称为 ANSI 编码。在简体中文系统下，ANSI 编码代表 GB2312 编码，在日文操作系统下，ANSI 编码代表 JIS 编码。</div>
<div>不同 ANSI 编码之间互不兼容，当信息在国际间交流时，无法将属于两种语言的文字，存储在同一段 ANSI 编码的文本中。</div>
<div>中文DOS、中文/日文Windows 95/98时代系统内码使用的是ANSI编码（本地化）</div>
<div>在使用ANSI编码支持多语言阶段，每个字符使用一个字节或多个字节来表示（MBCS，Multi-Byte Character System），因此，这种方式存放的字符也被称作多字节字符。比如，"中文123" 在中文 Windows 95 内存中为7个字节，每个汉字占2个字节，每个英文和数字字符占1个字节。</div>
<div>在非 Unicode 环境下，由于不同国家和地区采用的字符集不一致，很可能出现无法正常显示所有字符的情况。微软公司使用了代码页（Codepage）转换表的技术来过渡性的部分解决这一问题，即通过指定的转换表将非 Unicode 的字符编码转换为同一字符对应的系统内部使用的 Unicode 编码。可以在“语言与区域设置”中选择一个代码页作为非 Unicode 编码所采用的默认编码方式，如936为简体中文GBK，950为正体中文Big5（皆指PC上使用的）。在这种情况下，一些非英语的欧洲语言编写的软件和文档很可能出现乱码。而将代码页设置为相应语言中文处理又会出现问题，这一情况无法避免。从根本上说，完全采用统一编码才是解决之道，但目前尚无法做到这一点。</div>
<div>　　代码页技术现在广泛为各种平台所采用。UTF-7 的代码页是65000，UTF-8 的代码页是65001。</div>
<div><strong>3.3 Unicode编码</strong></div>
<div>为了使国际间信息交流更加方便，国际组织制定了 UNICODE 字符集，为各种语言中的每一个字符设定了统一并且唯一的数字编号，以满足跨语言、跨平台进行文本转换、处理的要求。</div>
<div>Unicode字符集可以简写为UCS（Unicode Character Set）。早期的unicodeUnicode标准有UCS-2、UCS-4的说法。UCS-2用两个字节编码，UCS-4用4个字节编码。</div>
<div>在 UNICODE 被采用之后，计算机存放字符串时，改为存放每个字符在 UNICODE 字符集中的序号。目前计算机一般使用 2 个字节（16 位）来存放一个序号（DBCS,Double Byte Character System），因此，这种方式存放的字符也被称作宽字节字符。比如，字符串 "中文123" 在 Windows 2000 下，内存中实际存放的是 5 个序号，一共10个字节。</div>
<div>Unicode字符集包含了各种语言中使用到的所有“字符”。用来给 UNICODE 字符集编码的标准有很多种，比如：UTF-8, UTF-7, UTF-16, UnicodeLittle, UnicodeBig 等。</div>
<h2>4、常用编码规则</h2>
<div><strong>4.1 单字节字符编码</strong></div>
<div>（1）编码标准：ISO-8859-1。</div>
<div>（2）说明：最简单的编码规则，每一个字节直接作为一个 UNICODE 字符。比如，[0xD6, 0xD0] 这两个字节，通过 iso-8859-1 转化为字符串时，将直接得到 [0x00D6, 0x00D0] 两个 UNICODE 字符，即 "ÖÐ"。</div>
<div>反之，将 UNICODE 字符串通过 iso-8859-1 转化为字节串时，只能正常转化 0~255 范围的字符。</div>
<div><strong>4.2 ANSI编码</strong></div>
<div>（1）GB2312, BIG5, Shift_JIS, ISO-8859-2。</div>
<div>（2）把 UNICODE 字符串通过 ANSI 编码转化为“字节串”时，根据各自编码的规定，一个 UNICODE 字符可能转化成一个字节或多个字节。</div>
<div>反之，将字节串转化成字符串时，也可能多个字节转化成一个字符。比如，[0xD6, 0xD0] 这两个字节，通过 GB2312 转化为字符串时，将得到 [0x4E2D] 一个字符，即 '中' 字。</div>
<div>“ANSI 编码”的特点：</div>
<div>（1）这些“ANSI 编码标准”都只能处理各自语言范围之内的 UNICODE 字符。</div>
<div>（2）“UNICODE 字符”与“转换出来的字节”之间的关系是人为规定的。</div>
<div><strong>4.3 UNICODE编码</strong></div>
<div>（1）编码标准：UTF-8, UTF-16, UnicodeBig。</div>
<div>（2）与“ANSI 编码”类似的，把字符串通过 UNICODE 编码转化成“字节串”时，一个 UNICODE 字符可能转化成一个字节或多个字节。</div>
<div>与“ANSI 编码”不同的是：</div>
<div>（1）这些“UNICODE 编码”能够处理所有的 UNICODE 字符。</div>
<div>（2）“UNICODE 字符”与“转换出来的字节”之间是可以通过计算得到的。</div>
<div>我们实际上没有必要去深究每一种编码具体把某一个字符编码成了哪几个字节，我们只需要知道“编码”的概念就是把“字符”转化成“字节”就可以了。对于“UNICODE 编码”，由于它们是可以通过计算得到的，因此，在特殊的场合，我们可以去了解某一种“UNICODE 编码”是怎样的规则。</div>
<h2>5、编码的区别</h2>
<div><strong>5.1 GB2312、GBK和GB18030</strong></div>
<div>（1）GB2312</div>
<div>当中国人们得到计算机时，已经没有可以利用的字节状态来表示汉字，况且有6000多个常用汉字需要保存，于是想到把那些ASCII码中127号之后的奇异符号们直接取消掉, 规定：一个小于127的字符的意义与原来相同，但两个大于127的字符连在一起时，就表示一个汉字，前面的一个字节（称之为高字节）从0xA1用到0xF7，后面一个字节（低字节）从0xA1到0xFE，这样我们就可以组合出大约7000多个简体汉字了。在这些编码里，我们还把数学符号、罗马希腊的字母、日文的假名们都编进去了，连在 ASCII 里本来就有的数字、标点、字母都统统重新编了两个字节长的编码，这就是常说的"全角"字符，而原来在127号以下的那些就叫"半角"字符了。这种汉字方案叫做 "GB2312"。GB2312 是对 ASCII 的中文扩展。兼容ASCII。</div>
<div>（2）GBK</div>
<div>但是中国的汉字太多了，我们很快就就发现有许多人的人名没有办法在这里打出来，不得不继续把 GB2312 没有用到的码位找出来用上。后来还是不够用，于是干脆不再要求低字节一定是127号之后的内码，只要第一个字节是大于127就固定表示这是一个汉字的开始，不管后面跟的是不是扩展字符集里的内容。结果扩展之后的编码方案被称为 “GBK” 标准，GBK 包括了 GB2312 的所有内容，同时又增加了近20000个新的汉字（包括繁体字）和符号。</div>
<div>（3）GB18030</div>
<div>后来少数民族也要用电脑了，于是我们再扩展，又加了几千个新的少数民族的字，GBK 扩成了 GB18030。从此之后，中华民族的文化就可以在计算机时代中传承了。</div>
<div>中国的程序员们看到这一系列汉字编码的标准是好的，于是通称他们叫做 "DBCS"（Double Byte Charecter Set 双字节字符集）。在DBCS系列标准里，最大的特点是两字节长的汉字字符和一字节长的英文字符并存于同一套编码方案里，因此他们写的程序为了支持中文处理，必须要注意字串里的每一个字节的值，如果这个值是大于127的，那么就认为一个双字节字符集里的字符出现了。在这种情况下，"一个汉字算两个英文字符！"。然而，在Unicode环境下却并非总是如此。</div>
<div><strong>5.1 Unicode和BigEndianUnicode</strong></div>
<div>这两个指示存储顺序不同，如"A"的Unicode编码为6500，而BigEndianUnicode编码为0065。</div>
<div><strong>5.2 UTF-7、UTF-8和UTF-16</strong></div>
<div>在Unicode里，所有的字符被一视同仁。汉字不再使用“两个扩展ASCII”，而是使用“1个Unicode”，注意，现在的汉字是“一个字符”了，于是，拆字、统计字数这些问题也就自然而然的解决了。</div>
<div>但是，这个世界不是理想的，不可能在一夜之间所有的系统都使用Unicode来处理字符，所以Unicode在诞生之日，就必须考虑一个严峻的问题：和ASCII字符集之间的不兼容问题。</div>
<div>我们知道，ASCII字符是单个字节的，比如“A”的ASCII是65。而Unicode是双字节的，比如“A”的Unicode是0065，这就造成了一个非常大的问题：以前处理ASCII的那套机制不能被用来处理Unicode了。</div>
<div>另一个更加严重的问题是，C语言使用'\0'作为字符串结尾，而Unicode里恰恰有很多字符都有一个字节为0，这样一来，C语言的字符串函数将无法正常处理Unicode，除非把世界上所有用C写的程序以及他们所用的函数库全部换掉。</div>
<div>于是，比Unicode更伟大的东东诞生了，之所以说它更伟大是因为它让Unicode不再存在于纸上，而是真实的存在于我们大家的电脑中。那就是：UTF。</div>
<div>UTF= UCS Transformation Format，即UCS转换(传输)格式。</div>
<div>它是将Unicode编码规则和计算机的实际编码对应起来的一个规则。现在流行的UTF有2种：UTF-8和UTF-16。</div>
<div>这两种都是Unicode的编码实现。</div>
<div><strong>5.2.1 UTF-8</strong></div>
<div>UCS-2编码(16进制)   UTF-8 字节流(二进制)</div>
<div>0000 - 007F         0xxxxxxx</div>
<div>0080 - 07FF         110xxxxx 10xxxxxx</div>
<div>0800 - FFFF         1110xxxx 10xxxxxx 10xxxxxx</div>
<div>例如“汉”字的Unicode编码是6C49。6C49在0800-FFFF之间，所以肯定要用3字节模板了：1110xxxx 10xxxxxx 10xxxxxx。将6C49写成二进制是：0110 110001 001001，用这个比特流依次代替模板中的x，得到：11100110 10110001 10001001，即E6 B1 89。</div>
<div>可见UTF-8是变长的，将Unicode编码为00000000-0000007F的字符，用单个字节来表示； 00000080-000007FF的字符用两个字节表示；00000800-0000FFFF的字符用3字节表示。因为目前为止Unicode-16规范没有指定FFFF以上的字符，所以UTF-8最多是使用3个字节来表示一个字符。但理论上来说，UTF-8最多需要用6字节表示一个字符。</div>
<div>UTF-8兼容ASCII。</div>
<div>5.2.2 UTF-16（标准的Unicode成为UTF-16）</div>
<div>UTF-16和上面提到的Unicode本身的编码规范是一致的。</div>
<div>UTF-16以16位为单元对UCS进行编码。对于小于0x10000的UCS码，UTF-16编码就等于UCS码对应的16位无符号整数。对于不小于0x10000的UCS码，定义了一个算法。不过由于实际使用的UCS2，或者UCS4的BMP必然小于0x10000，所以就目前而言，可以认为UTF-16和UCS-2基本相同。但UCS-2只是一个编码方案，UTF-16却要用于实际的传输，所以就不得不考虑字节序的问题。</div>
<div>UTF-16不兼容ASCII。</div>
<div><strong>5.2.3 UTF-7</strong></div>
<div>UTF-7 (7-位元 Unicode 转换格式（Unicode Transformation Format，简写成 UTF）) 是一种可变长度字元编码方式，用以将 Unicode 字元以 ASCII 编码的字元串来呈现，可以应用在电子邮件传输之类的应用。</div>
<div>UTF-7并非Unicode标准之一。想要详细了解的可以查阅相关资料。</div>
&nbsp;
编码系列1：<a href="http://sqh.me/blog/?p=263">编码那点事----历史进化</a>
编码系列2：<a href="http://sqh.me/blog/?p=273">字符编码详解 part1</a>
编码系列3：<a href="http://sqh.me/blog/?p=275">字符编码详解 part2</a>
