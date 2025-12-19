---
authors:
  - name: null
---

# 2 Creating Databases and Spreadsheets

## 2.1 General Considerations

As stated previously, it is not the place of this guide to provide guidance on creation of either spreadsheets or databases beyond considerations that have a significant impact upon the preservation of a certain type of dataset. The following are general pointers on ensuring that data is both consistent and easily reusable and remains so throughout its preservation lifecycle.

* Use controlled vocabularies and established word lists where possible for data entry in both spreadsheets and databases.
* Adhere to consistent and meaningful table/sheet and field/column naming conventions and be aware that tables or sheets may not always remain packaged together within a single file. Also be aware that some applications restrict the use of the certain field names (e.g. ORACLE cannot have tables that start with a number or fields named 'desc' or 'date') or even the use of spaces within field or column names. While some applications allow these, such elements are best avoided as they can present a problem in future data migrations.
* In spreadsheets, don't use styles and formatting to convey meaning as this can be lost when the data is migrated or used within different applications.

## 2.2 File types

The table below outlines some of the common formats used to create spreadsheets and databases and describes their associated applications and potential uses for long term preservation. As with many word processing applications, spreadsheets in particular have seen a move in recent years towards support for common XML-based file formats and it is worth noting that many applications such as Microsoft Office, OpenOffice and WordPerfect Office have support for both Office Open XML (OOXML) and OpenDocument Format (ODF) file formats.

### Databases

```{list-table}
:header-rows: 1

* - Format
  - Properties/Technologies
  - Description
  - Recommendations
* - .accdb
  - Proprietary Microsoft format used by [Access databases](https://support.microsoft.com/en-us/access?legRedir=true) (2007 onwards)
  - The .accdb format was first introduced in Access 2007 and continued with Access 2010 and was developed in order to include enhanced functionality over the previous .mdb format. It is arguable that, from a robust database design standpoint, additional functions and enhancements such as Multivalued Fields and Attachments only increase the difficulty in preserving such databases. It is also worth noting that, although the format is the default in Access 2007 and 2010, files created in Access 2010 may not be completely compatible with Access 2007. The .accdb format, as with previous .mdb files, continues to be based on the Jet Database Engine.
  - The .accdb format is not recommended for long term storage but Access does support output in a number of suitable formats.
* - .mdb
  - Proprietary Microsoft format used by Access databases (2003 and earlier)
  - Proprietary Microsoft format now replaced by the .accdb format. In essence, the .mdb format packages up the Access interface with the actual database engine (Jet Database Engine). Inevitably there have been updates to Jet (Access 2.0 uses version 2.5, Access 95 uses version 3.0, Access 97 uses version 3.5, Access 2000 – 2003 use version 4.0) with the result that there have been format changes to the .mdb file. Particular issues have been notes between Jet versions 2 and 3 and it is possible that versions of Access using Jet versions below 3 are probably currently inaccessible.
  - The .mdb format is not recommended for preservation but Access supports output in a number of suitable formats.
* - .odb
  - An XML-based database format used by OpenOffice Base
  - Although most commonly seen and used as a part of the OpenOffice suite, the .odb format was not part of the original OASIS OpenDocument (@oasis2005open, ISO and IEC standard) specification. Like ODF formats however, an .odb file consists of a series of zipped XML files where content is contained in a 'content' xml subdocument and additional subdocuments contain style information, document metadata, and application-specific settings. In addition, .odb - like Access formats - also consists of an interface (which can access external data sources) and a database engine (in this case, the [HSQL](https://hsqldb.org/) database engine).
  - The .odb format is not recommended for long term storage but many of the applications that use this format (especially OpenOffice) support output in a number of suitable formats.
* - .dbf (also .dbt and .ndx)
  - Originally used by dBASE but also adopted by others (e.g. ESRI for ArcInfo)
  - The format was originally developed in the 1980s for dBASE but has emerged as a generic format with a number of (often incompatible) variations, often referred to as '[xBase](https://www.clicketyclick.dk/databases/xbase/format/index.html)'. Although the file structure is simple and documented it is important to be aware of the specific software application used in creating the file.
  - The format has potential for long-term storage but, due to variations on the standard, it is important to know exactly how the file has been created. dBase, as with most applications, supports output to more suitable formats.
```

### Spreadsheets

```{list-table}
:header-rows: 1

* - Format
  - Properties/Technologies
  - Description
  - Recommendations
* - .xls
  - A proprietary binary format used by Microsoft Excel (up to Excel 2003)
  - Although a proprietary Microsoft format, the Excel .xls format is widely used and can be imported by a number of third-party applications (e.g. OpenOffice and Google Docs). The format has been replaced by XML based formats (notably .xlsx) in versions of Microsoft Office since 2003
  - Although compatible with other open applications, the xls format is no longer the default format for Excel files (see .xlsx below) and is not recommended for long-term preservation.
* - .xlsx
  - Part of the Office Open XML (OOXML) format created by Microsoft. An ECMA and [ISO](https://www.iso.org/standard/51463.html) standard.
  - A relatively new format from Microsoft, released with Office 2007. They chose to develop their own specification (OOXML) rather than use the existing ODF international standard. The format consists of human readable XML files packed with other content within a single zipped file.
  - As a documented and open standard, .xlsx is in theory suitable for long-term preservation although embedded content should be stored separately. The final file is essentially a zipped archive and may also be best to store the content in an uncompressed format. As with all spreadsheet data, the ability to migrate to a plain text format should be considered for maximum accessibility.
* - .sxc
  - Part of the OpenOffice XML suite of formats and used by OpenOffice 1.0 Calc (now replaced by .ods)
  - The OpenOffice XML sxc format (now replaced by the OpenDocument .ods format) is, like its successor, an XML based format. The format is still supported by a number of applications including OpenOffice. The format itself consists of a compressed XML file, with the actual spreadsheet data being stored in a file and images and other content in a separate directory.
  - While an open and text based format, it is recommended that the newer .ods is used in preference to .sxc.
* - .ods
  - Part of the OpenDocument suite of formats, an ISO standard [ISO/IEC 26300:2006](https://www.iso.org/standard/43485.html) for XML-based office document formats. Primarily used by OpenOffice Calc (version 2.0 onwards).
  - As with the OpenDocument Text (.odt) format, the .ods file is essentially a compressed zip file containing separate style, text (as XML) and embedded content (e.g. images) files.
  - As an open XML-based format, .ods is suitable for long-term preservation though ideally the files should be stored in their uncompressed form. Additionally, where the document contains images or other content, these should ideally be stored separately in a suitable preservation format.  Ods can be used as a format for preservation where csv is not able to adequately preserve all the significant properties of a file. It may be worth trying file conversions to xlsx too in order to see which is most effective. Note that Calc provides character set options when exporting to csv. This is a good option if conversion from xls to csv with UTF-8 encoding is required.
* - .123 and .wk* (e.g. .wk4, .wks, etc.)
  - Files created by the Lotus 1-2-3 spreadsheet application. Binary and proprietary formats.
  - Lotus 1-2-3 was a popular application in the 1980s and 1990s but has ceased development since 2002. The file formats can be read into either MS Excel 2000 OpenOffice Calc where they can be converted into a more suitable format
  - This format is not recommended for long-term preservation and there may be issues when files are converted using other office software (e.g. functions and formulas may be calculated in a different way or be unavailable). It is particularly important therefore that full documentation is supplied explaining any important additional features and functionality.
* - *.wq* /.qpw
  - Files created by Quattro Pro (now part of the WordPerfect Office Suite)
  - A proprietary format used by the Quattro Pro spreadsheet application.  Older files are also supported by Microsoft Excel 2000 (for Quattro Pro for Windows versions 1-5 the Quattro Pro Converter will need to be installed) but there can be problems importing these files into Excel e.g. graphs, embedded objects and macros in Quattro Pro for Windows are lost when the file is imported into Excel. Current versions of Quattro Pro support OOXML formats.
  - Not recommended as a format for long-term storage and files should be exported in an XML or plain text-based format.
```