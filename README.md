# SMuFL Supports for Glyphsapp

本仓库提供字体编辑软件Glyphs的配置文件，使其在语言、侧边栏中显示所有SMuFL字符。

This package provides configuration files for the Glyphs font editing software, which make it possible to show all the SMuFL Glyphs in Languages and Categories.

> [!TIP]
>
> SMuFL 官方也为 Glyphs 用户提供了实用的脚本，见下文 [可能派上用场的链接](#jump1)。
>
> SMuFL Group also provides useful scripts for Glyphs users, see below [Useful stuffs](#jump1) .



## 预览 / Previews

<p align=center>
<img alt="Startup Window" src="https://github.com/Musanyu-Music/SMuFL-for-Glyphsapp/blob/main/resources/pics/startup.png" /><br/>
Startup Window
</p>

<p align=center>
<img alt="Sidebar" height=500 src="https://github.com/Musanyu-Music/SMuFL-for-Glyphsapp/blob/main/resources/pics/sidebar.png" /><br/>
Sidebar
</p>




## 安装 / Installation

在右方的Release中下载压缩包并解压，把其中的文件拷贝到如下路径：

Download then unpack the .7z file from Releases, and copy the files to the following path:

```
~/Library/Application Support/Glyphs 3/
```

> [!WARNING]
>
> ⚠️ 请注意，如果已经存在同名文件夹，**请不要直接覆盖！！**请打开同名的文件夹将文件一个个拷贝到里面，**否则可能导致您的文件丢失！**
>
> ⚠️ Please note that if a folder with the same name already exists, **DO NOT OVERWRITE IT DIRECTLY!!** Please open the folder and copy the files into it individually, **otherwise your files may be lost! **



正确的文件结构应该如下所示：

The correct path should be as follows:

<p align=center>
<img alt="The Correct Path" height=450 src="https://github.com/Musanyu-Music/SMuFL-for-Glyphsapp/blob/main/resources/pics/path.png" /><br/>
The Correct Path
</p>




## 说明 / Instructions

> [!NOTE]
>
> 所有配置文件都基于 Standard Music Font Layout (SMuFL) Version 1.5进行制作。
>
> All these files are based on Standard Music Font Layout (SMuFL) Version 1.5.
>
> 参考文件 / References：
>
> 1. [Standard Music Font Layout (SMuFL)](https://w3c.github.io/smufl/latest/index.html#standard-music-font-layout-smufl) (SMuFL official website)
> 2. https://github.com/w3c/smufl/tree/gh-pages/metadata (Original Files of *glyphnames.json*, *classes.json* and *ranges.json*)

- ### GlyphData-SMuFL.xml

包含了SMuFL标准所提供的  *glyphnames.json* 中所有字符。让Glyphs能够将SMuFL所使用的所有unicode码位对应到SMuFL标准所提供的字符名称上。

Contains all the glyphs in *glyphnames.json* provided by the SMuFL standard. This allows Glyphs to map all unicode code points used by SMuFL to the glyph names provided by the SMuFL standard.

> [!IMPORTANT]
>
> 在 *glyphnames.json* 中，SMuFL提供了4个未被使用的码位（如下所示），虽然它们已经以 ~Unused 的名称存在于 *GlyphData-SMuFL.xml* 中（可以在app的字符型信息面板中搜索到并添加到字体中），但已经在 侧边栏的Categories 和 Languages 中被剔除。
>
> In *glyphnames.json*, SMuFL provides 4 unused code points (as shown below). Although they already exist in *GlyphData-SMuFL.xml* with the name ~Unused (which can be searched and added in the Glyph Info window of the app), they have been removed from Categories and Languages in the sidebars.
>
> ```
> accSagittalUnused1,
> accSagittalUnused2,
> accSagittalUnused3,
> accSagittalUnused4.
> ```



- ### Groups-SMuFL.xml

使Glyphs能够在启动界面和侧边栏中显示SMuFL语言和分类；

Allow Glyphs to display SMuFL languages and categories in the launcher and sidebar;



1. #### Categories

   Categories采用两种分类方式，分别按照 SMuFL 标准提供的 *classes.json* 和 *ranges.json* 进行分类，并按照A-Z升序排列，方便用户检索。

   There are two classification methods in Categories, which are classified according to the *classes.json* and *ranges.json* provided by the SMuFL standard, and arranged in ascending order from A to Z for user retrieval convenience.

   <div align=center><img alt="Categories" height=450 src="https://github.com/Musanyu-Music/SMuFL-for-Glyphsapp/blob/main/resources/pics/classes.png" /><img alt="Categories" height=450 src="https://github.com/Musanyu-Music/SMuFL-for-Glyphsapp/blob/main/resources/pics/ranges.png" /> <br/><p align=center>
     Categories
     </p></div>
   
   
   
   
   
2. #### Languages

   Languages主要采用 *ranges.json* 中提供的分类依据来进行分组，不同的是作者将其进一步细分，使用了更易于人检索和查找的形式。
   
   Languages are mainly grouped using the classification criteria provided in *ranges.json*. The difference is that the author further subdivides them and uses a form that is easier for people to search and find.
   
   <p align=center>
   <img alt="Languages" height=450 src="https://github.com/Musanyu-Music/SMuFL-for-Glyphsapp/blob/main/resources/pics/languages2.png" /><br/>
   Languages
   </p>
   
   
   

- ### Groups-SMuFL_Basics.plist

这是一个可选的文件，用户可以按照自己需求选择是否使用这个文件。

This is an optional file. Users can choose whether to use this file according to their needs.



SMuFL提供了尤其庞大的字符库，除了 Bravura 以外，还未有兼容所有 SMuFL Unicode 码位的音乐字体（截止至2025年1月31日）。对于普通的乐谱制作者来说，创造一个兼容所有 SMuFL 字符的字体几乎是不可能的，他们甚至一辈子都不会用到 SMuFL 字符库里那些冷门的字符。

SMuFL provides a particularly large character library. Except for Bravura, there is no music font that is compatible with all SMuFL Unicode code points (as of January 31, 2025). For ordinary music engravers, it is almost impossible to create a font that is compatible with all SMuFL characters. They may never use those unusual glyphs in the SMuFL in their lifetime.



所以笔者删除了一些几乎不会用到，或者是就算使用也不会优先从音乐字体中调用的字符，制作了一个更直观简易、易读性更强的分类，并给它们都加上了图标。可能适合字体制作者起步使用。

So I deleted some characters that are rarely used, or have the least priorities, and made a more intuitive, simple and readable classification, and added icons to them. It may be a good starter for beginners.

<p align=center>
<img alt="Basics" height=300 src="https://github.com/Musanyu-Music/SMuFL-for-Glyphsapp/blob/main/resources/pics/basics.png" /><br/>
Basics
</p>


> [!IMPORTANT]
>
> 一个音乐字体所需要的字型，根据其兼容的软件以及其排版风格会有非常大的差距。*Groups-SMuFL_Basics.plist* 中所列出来的并不代表每个字体都需要绘制的字形，也不代表初学者只能从这些字形开始绘制。建议每一个制作 SMuFL 字体的人都认真阅读 SMuFL 官方文档，并使用一款成熟的字体（例如Bravura）作为参考。
>
> The glyphs required for a music font vary greatly depending on the software it is compatible with and its typesetting style, for instance. The glyphs listed in *Groups-SMuFL_Basics.plist* **DO NOT** represent the glyphs that need to be drawn for every font, **NOR** do they mean that beginners can only start with these glyphs. It is recommended that everyone who makes SMuFL fonts carefully read the SMuFL official documentation and use another commercial font (such as Bravura) as a reference.



- ### CustomFilterSMuFL.plist

<p align=center>
<img alt="Filters" height=300 src="https://github.com/Musanyu-Music/SMuFL-for-Glyphsapp/blob/main/resources/pics/filters.png" /><br/>
Filters
</p>

提供了5个筛选器，它们分别是：

Providing 5 filters :

```
Optional Glyphs Code Range
Used Optional Glyphs
Used Non-SMuFL Range Glyphs
Unicode Music Symbols Code Range
Used Unicode Music Symbols
```

1. #### Optional Glyphs Code Range

   根据 SMuFL 标准（查看文档：[optionalGlyphs](https://w3c.github.io/smufl/latest/specification/optionalglyphs.html)），在码位 U+F400–U+FFFF 之内可以给字体存放各种可选的替代字符。这些码位并不包含在 *ranges.json* 和 *classes.json* 中，也就意味着没有办法从侧边栏的 Categories 和 Languages 中找到并使用这些字符。

   According to the SMuFL standard (see the document: [optionalGlyphs](https://w3c.github.io/smufl/latest/specification/optionalglyphs.html)), the code range U+F400–U+FFFF can be used to store various optional glyphs for the stylistic alternates. This code range is not included in *ranges.json* and *classes.json*, which means that there is no way to find and use these characters from the Categories and Languages in the sidebar.

   

   这是一个List Filter，也就意味着用户可以在此右击，方便地根据自己的需要添加需要的字符，来存放替代字符。

   This is a List Filter, which means that users can right-click here to conveniently add the required characters according to their needs to store the replacement characters.

   

2. #### Used Optional Glyphs

   这是一个Smart Filter，用来显示在Optional Glyphs Code Range中已经被使用的字符。

   This is a Smart Filter that is used to display the characters that have been used in the Optional Glyphs Code Range.

   

3. #### Used Non-SMuFL Range Glyphs

   通常，SMuFL 字体并不会只使用 SMuFL 的编码范围，有时候还会使用非 SMuFL 码位的字符。这个Smart Filter是专门用来显示那些不在 SMuFL 编码区中的字符的。

   Usually, SMuFL fonts do not use only the SMuFL code range, but sometimes use non-SMuFL code points. This Smart Filter is specifically used to display characters that are not in the SMuFL code range.

   

4. #### Unicode Music Symbols Code Range

   为了与文本编辑器兼容，不少 SMuFL 标准字体还会将对应的字符再存放一份在Unicode Music Symbols Code Range中。这是一个 List Filter，用户可以右键选择并添加想要的 Unicode Music Symbols 字符。

   In order to be compatible with text editors, some SMuFL standard fonts also copy the corresponding characters in the Unicode Music Symbols Code Range. This is a List Filter, users can right-click and add the Unicode Music Symbols glyphs as they want.

   

   > [!NOTE]
   >
   > 从U+1D100到U+1D1FF都是Unicode Music Symbols Code Range（一共256个字符），而最后 21 个字符是闲置的。此列表包括了这些闲置字符。
   >
   > The Unicode Music Symbols Code Range starts from U+1D100 and ends at U+1D1FF (256 characters long). The last 21 characters are unused, this list includes these unused characters.

   

5. #### Used Unicode Music Symbols

   这是Smart Filter，用来显示已经使用的Unicode Music Symbols。
   
   This is a Smart Filter that displays all the used Unicode Music Symbols.



## 作者 / Contributor

此文件由木三聿制作。

These files were created by Musanyu.



## 版权 / License

免费使用，免费分享。Under GNU GPL v3.0.

Free to use and share. Under GNU GPL v3.0.



## 可能派上用场的链接 / Useful stuffs

- SMuFL Documents : https://w3c.github.io/smufl/latest/index.html
- <span id="jump1">**<u>Official scripts for Glyphsapp</u>**</span>  : https://github.com/w3c/smufl/tree/gh-pages/scripts/glyphsapp
- **SMuFL Group's offical Github link** : https://github.com/w3c/smufl/tree/gh-pages