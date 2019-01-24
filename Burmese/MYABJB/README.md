# The Burmese Bible translation by Adoniram Judson 1835 in USFM format
## မြန်မာယူနီကုတ်

[Adoniram Judson](https://en.wikipedia.org/wiki/Adoniram_Judson) made the first complete translation of the Bible from the original languages into Burmese, on by 31 January 1834. After this, he continued to revise it. He completed a revision of the Old Testament on 26 September 1835, a revision of the New Testament on 22 March 1837, and a revision of the entire bible, published in quarto format, on 24 October 1840. _See [Bible translations into Burmese](https://en.wikipedia.org/wiki/Bible_translations_into_Burmese) on Wikipedia._

### Source
The [Crosswire Project](https://gitlab.com/crosswire-bible-society/burjudson)


### Font
To display the Burmese script requires a smart font engine and a suitable font. We recommend the [SIL Padauk](http://scripts.sil.org/Padauk) font.

### Previous revision history
1. The USFM files were reverse engineered in January 2019 from an earlier merged OSIS XML file that was generated in 2011 - the one used for BurJudson module **version 1.3**.
2. The conversion to USFM improved the markup and also tidied up the text a little. i.e.
There were no compound hyphenated words in the text so hyphens were replaced by a horizontal bar (quotation dash).
Multiple whitespace was also removed.
3. The merged OSIS XML file was derived from the 66 individual XML files (_see below_).
   This repaired several osisID errors and also included a general tidy up.
4. The Judson text was originally keyed in Microsoft Word™ sometime during 2006, from which it was exported by Keith Stribley into OSIS.
   During this period Keith was assisting in the **Myanmar Bibles Software Project** then being led by [Levi Sap Nei Thang](https://www.levithang.com/pages/about-me).
5. Those OSIS files were refreshed in February 2010, but very few text developers would be aware of that.
   The refresh fixed an earlier textual error; viz. the  omission of **Titus 3:9-15**.
   _That omission had actually been due to an XML markup error that caused those 7 verses to be hidden._

### Acknowledgement
* To the late **Keith Stribley** who kindly supplied these XML files in 2010.
* Keith died in February 2011. See [In Memoriam Keith Stribley](https://ultimategerardm.blogspot.com/2011/02/in-memoriam-keith-stribley.html).
* Gerard Meijssen's "In Memoriam" page contains several broken links.  i.e. The links to Keith's former website at _thanlwinsoft.org_
* Try instead this WayBack Machine [snapshot](https://web.archive.org/web/20100409092637/http://thanlwinsoft.org/).

### Textual issues

##### Linked verses:
* There are 125 linked verses (71 verse ranges) in total.
* I have uploaded (FIO) a list of the locations.
* _These are not a problem that needs to be solved._
* NB. Keith's OSIS files omitted the inner **osisID**s for ranges with more than two verses.
* _This error was fixed when the indivdual OSIS files were converted to a single file in 2012._

##### Missing verses:
(_Relative to the KJV versification_)
* Numbers 8:26, II Kings 11:21, **I Chronicles 9:35-44**, II Chronicles 36:22-23.
* _These were reported to Myanmar Bibles in 2012. Still awaiting a response._

##### Extra verse:
* Psalms 58:12 is not in the KJV versification. 

##### Misplaced text:
* Song 8:5b is somehow shifted into the `\mte ` line and needs to be fixed.

##### Character differences:
Compared to the text of our BurJudson module **version 1.1** there are 281 text differences regarding
* U+1025 MYANMAR LETTER U and 
* U+1009 MYANMAR LETTER NYA

These two characters have some visual similarity, so they may be typographical errors. Whether the new text or the old is correct in these locations is still unresolved. _This issue has not yet been reported in detail to Myanmar Bibles._

I have uploaded a _character frequency_ analysis of the OSIS file that I generated using **BabelPad** on 2011-12-08.

##### Minor textual differences:
Compared to the text used for making BurJudson module **version 1.2** there are 12 further unresolved minor text differences at identified locations. _These have not yet been reported to Myanmar Bibles._

##### Paragraph tags `\p`
The USFM `\p` tags correspond to where the XML files had the start of the &lt;p&gt; element. Whether all these accurately reflect paragraph starts in the printed Bible has not been checked.

* Initial `\p` tags were moved to below the chapter label and title.
* Multiple consecutive `\p` tags were reduced to one.

##### End main titles: `\mte `
With the exception of **I Samuel**, each book also contains an end main title. These titles appear after the last verse of the last chapter in each book.
* In Keith's OSIS, these were enclosed within a **div** element with type="afterword".
* Psalms & Song both have a line or two of text just after the \mte line. _Being reviewed._
* The end titles after Malachi and Revelation also refer to the end of the OT and NT respectively.

##### Chapter labels: `\cl `
The former 1189 preverse titles that were chapter numbers in Burmese script are simply changed to chapter labels in the USFM files. These become milestone elements in the OSIS file generated by adyeths/u2o script. 

##### Psalm titles: `\d `
There are currently only 19 Psalms with a canonical title, leaving 97 Psalms still without such a title. Further research is required to restore these to the source text.

##### Book names: `\mt `
There are subtle differences between some of the book names in the Myanmar Bibles webpage menu (& its navigation script) compared to the book names in the USFM files. The 66 Burmese book names should be further reviewed for semantics, spelling & punctuation.
* The Excel file in the **Analysis** folder tables and compares these titles. _Further work required._

##### Notes: `\f ...\f*` & `\x ...\x*`
The digital text currently has no notes, though it's possible that some later printed editions have footnotes and cross-references. _Further research required._

##### Processing
Bespoke TextPipe filters were used for the following conversions:
1. From individual OSIS files to a single OSIS file (2012)
2. From a single OSIS file to a single USFM file (2019)
3. From a single USFM file to separate USFM files (2019)

_The last step does not involve any textual changes._

* The output USFM files are renamed _en bloc_ using a Windows CMD file.
FIO. I have uploaded a **USFM Tag Statistics** file to the Analysis folder.