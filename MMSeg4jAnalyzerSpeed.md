看一下 mmseg4j 的分词速度如何，下载了两篇长篇小说共2.5M左右，可以到 <a href='http://mmseg4j.googlecode.com/files/txt.zip'><a href='http://mmseg4j.googlecode.com/files/txt.zip'>http://mmseg4j.googlecode.com/files/txt.zip</a></a>。2.5M的数据，用Complex模式是 5.3秒左右，不知是快还是慢（因为没有对比），Simple 模式用了2.9秒(AMD athlon 64 2800+ 1G内存 xp)。

代码有两个版本：用Analyzer方式的和不依赖Lucene Analyzer方式的，前者比较简洁


可以到 svn 上看：<a href='http://mmseg4j.googlecode.com/svn/trunk/example/com/chenlb/mmseg4j/example/'><a href='http://mmseg4j.googlecode.com/svn/trunk/example/com/chenlb/mmseg4j/example/'>http://mmseg4j.googlecode.com/svn/trunk/example/com/chenlb/mmseg4j/example/</a></a>，源码。

运行：

<pre>
M:\eclipse 3.3.2\workspace\mmseg4j>java -cp bin -Djava.ext.dirs=lib com.chenlb.mmseg4j.example.PerformanceAnalyzer txt<br>
Mar 28, 2009 4:35:02 PM com.chenlb.mmseg4j.Dictionary <init><br>
信息: look up in mmseg.dic.path=null<br>
Mar 28, 2009 4:35:02 PM com.chenlb.mmseg4j.Dictionary <init><br>
信息: look up in user.dir=M:\eclipse 3.3.2\workspace\mmseg4j/data<br>
Mar 28, 2009 4:35:03 PM com.chenlb.mmseg4j.Dictionary init<br>
信息: chars loaded time=266ms, line=12638, on file=M:\eclipse 3.3.2\workspace\mmseg4j\data\chars.dic<br>
Mar 28, 2009 4:35:03 PM com.chenlb.mmseg4j.Dictionary init<br>
信息: words loaded time=469ms, line=120330, on file=M:\eclipse 3.3.2\workspace\mmseg4j\data\words.dic<br>
Mar 28, 2009 4:35:03 PM com.chenlb.mmseg4j.Dictionary init<br>
信息: sort time=109ms<br>
Mar 28, 2009 4:35:03 PM com.chenlb.mmseg4j.Dictionary init<br>
信息: load dic use time=859ms<br>
use 4921ms<br>
</pre>

simple 模式：
<pre>

M:\eclipse 3.3.2\workspace\mmseg4j>java -cp bin -Djava.ext.dirs=lib -Dmode=simple com.chenlb.mmseg4j.example.PerformanceAnalyzer txt<br>
Mar 28, 2009 4:35:29 PM com.chenlb.mmseg4j.Dictionary <init><br>
信息: look up in mmseg.dic.path=null<br>
Mar 28, 2009 4:35:29 PM com.chenlb.mmseg4j.Dictionary <init><br>
信息: look up in user.dir=M:\eclipse 3.3.2\workspace\mmseg4j/data<br>
Mar 28, 2009 4:35:29 PM com.chenlb.mmseg4j.Dictionary init<br>
信息: chars loaded time=203ms, line=12638, on file=M:\eclipse 3.3.2\workspace\mmseg4j\data\chars.dic<br>
Mar 28, 2009 4:35:29 PM com.chenlb.mmseg4j.Dictionary init<br>
信息: words loaded time=266ms, line=120330, on file=M:\eclipse 3.3.2\workspace\mmseg4j\data\words.dic<br>
Mar 28, 2009 4:35:29 PM com.chenlb.mmseg4j.Dictionary init<br>
信息: sort time=78ms<br>
Mar 28, 2009 4:35:29 PM com.chenlb.mmseg4j.Dictionary init<br>
信息: load dic use time=547ms<br>
use 2421ms<br>
</pre>