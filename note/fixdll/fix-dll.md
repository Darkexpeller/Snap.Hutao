
在最新SnapHutao存档中，使用VS进行编译会出现报错，原因为依赖包Snap.Hutao.SourceGeneration(Version=1.3.13)使用了原官方网站的接口：

<img src="https://github.com/Darkexpeller/Snap.Hutao/tree/main/note/fixdll/ffc066a4eb9a7afb3e55e955c30cf18a.png">

<img src="https://github.com/Darkexpeller/Snap.Hutao/tree/main/note/fixdll/476b93c74749adc98e01334887a5c95f.png">

由于网站已经关停，因此该源生成器会产生报错，编译无法正常通过。

一个临时的解决办法为通过dnSpy等软件对该依赖的dll文件进行修改，将该链接替换为可访问接口。对已发布程序进行逆向和该生成器代码逻辑进行分析可看出该接口返回内容为一json数据，因此在此直接给出替换链接与修改后的dll文件:

[Last文件](https://github.com/Darkexpeller/Snap.Hutao/tree/main/res/Archive/Salt/Last)

[DLL文件](https://github.com/Darkexpeller/Snap.Hutao/tree/main/res/lib/Snap.Hutao.SourceGeneration.dll)

可通过VS解决方案管理器查询该包路径，进行替换即可。