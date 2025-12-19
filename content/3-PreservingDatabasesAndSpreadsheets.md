---
authors:
  - name: null
---

# 3 Archiving Databases and Spreadsheets

## 3.1 Deciding Which Files to Archive

As with text documents, spreadsheets and databases largely remain in a single format throughout their creation period. They are also largely self-contained in that they seldom include imported images or other media within the file. Where this does happen, however, it is recommended that embedded content is stored separately in order that these files can follow a separate relevant preservation path.

## 3.2 Deciding How to Archive

As far as many archives are concerned the core of both a spreadsheet and a database are the data tables/worksheets themselves along with documentation and metadata describing the contents of and relationships between tables or sheets. The order or layout of the columns and rows may also be of significance (especially in spreadsheets where layout is significant) but forms, reports, queries and macros are not seen as core data and are therefore often not preserved.

__Significant properties__

The significant properties - i.e. the most basic elements of a file that are to be preserved and maintained - are outlined below:

* __Values__ - The actual data within the spreadsheet or database (there may be several sheets of data or tables) including cell headings and the values themselves
* __Graphics__ - Any figures, graphs or charts in the spreadsheet. Databases rarely allow objects to be embedded within them and more frequently link to external files. It is, however, important to be aware that such functionality is emerging and may be used in newer databases (e.g. Access .accdb files).
* __Layout__ - With spreadsheets in particular, where formatting and the use of colour or certain styles is seen as adding meaning to the data, this meaning becomes a significant property and must be preserved in some way. This is commonly seen where spreadsheets are used as a means to layout tabular data (which is often better done using word processing software), in such cases alternative formats (e.g. PDF) should be used to preserve data as such formatting is generally lost when exporting to plain text based formats.
* __Relationships__ - Particularly with databases though also applicable to spreadsheets, it is important that the relationships between tables/sheets are documented and understood.

__General Checks__

In addition to ensuring that the significant properties of a file are retained during any file conversions, there are certain checks to be made before a conversion can be carried out. These checks ensure that certain significant characteristics of a spreadsheet or database are not lost during the conversion process.

* __Layout and Formatting__ - As mentioned above, layout and formatting, especially in spreadsheets, can be problematic when used to convey additional meaning and can present issues when migrating data to delimited text formats. Checks should be made for headings that span multiple rows or columns or information conveyed through use of colour, borders or font. Depending on the nature of the formatting, either the data will need to be edited by hand before migration to ensure that meaning is not lost (e.g. with spreadsheets, merged cells must be split and the text within them duplicated within each cell) or an alternative migration format should be found.

* __Tables and Sheets__ - Although it should be assumed that databases or spreadsheets should be migrated in their entirety, an assessment of each file should be made in order to establish which tables or sheets should be migrated. Often spreadsheets contain a default number of blank worksheets when created and users often create additional sheets - or tables in databases - to temporarily store data which are not intended for preservation.

* __Formulae, Queries, Macros__ - If the file contains complex formulae or queries that need to be preserved in their own right then these need to be identified as migrated versions of the spreadsheet or database may only preserve the actual values calculated by the functions and not the functions themselves. Complicated formulae (e.g. those linking worksheets) or queries may need to be preserved separately and documented within a text file so the spreadsheet functionality can be recreated at a later date.

* __Comments or Notes__ - As with macros and formulae, the migration process may not save comments or text notes added to a file. Before migration, comments will need to be stored in a separate text file with a clear indication of which file and cell the comment relates to.

* __Hidden or Protected Data__ - Occasionally spreadsheets contain hidden or protected cells. These should be identified so that the migration strategy includes such data.

* __Special Characters and Delimiters__ - Occasionally databases and spreadsheets can contain special characters or common delimiters (e.g. tabs or pipes) within the dataset. Delimiters such as pipes, commas or tabs can present a problem if the file is to be migrated to delimited text and such characters should be identified early on so that the migration strategy can account for them. In addition to delimiters, special or foreign characters such as ampersands, smart quotes or the em dash ("—") may also interfere with the export and subsequent display of the data. Databases and spreadsheets may also contain foreign characters which will often not export to a basic text file unless a specific character set (e.g. UTF-8) is specified. 

* __Links__ - With databases in particular it is important that the relationships between tables are understood, documented (see under 3.3 below) and are correct (checks can be made to ensure that duplicate or orphan records aren't present). Worksheets within spreadsheets can also be linked through cells drawing on the values from other sheets. Additionally, both databases and spreadsheets can link to (or hold the filenames of) files such as images that are held externally. If such external files are part of a project dataset then checks should be made to ensure that these filenames are stored correctly.

__File-naming__

Depending on how the data is to be preserved, it may be necessary to rename database tables and spreadsheet worksheets. If files are to be preserved as delimited text then, for both databases and spreadsheets, the final dataset will consist of a text file per table/worksheet. Where possible files should retain the same name as the original (though the file extension may be different). Where multiple worksheets or database tables are being exported, filenames should reflect both the name of the original spreadsheet/database and the name of the worksheet or table that the data came from, for example:

* _[database name]-[table name].txt_ e.g. findsdatabase-lithics.txt
* _[spreadsheet name]-[worksheet name].txt_ e.g. siteregister-photos.txt

Where extra files are created to hold images, queries, notes or formulae, these should also be named in logical way that makes it easy to trace exactly where they came from, e.g.'' [[spreadsheet name]-[[worksheet name]-[[chart name].tif''.

In some cases it may be necessary to change the table names to either shorten them or remove punctuation that cannot be used within a filename. In such cases it is important to remain as close to the original name as possible.

__File Formats__

For the majority of databases and spreadsheets, the preferred format for preserving data is as delimited text. However, as highlighted above, there are often stylistic or functional elements of a spreadsheet or database that can only be maintained within a certain format. In such cases it is recommended that a compatible open XML-based format (e.g. .ods or xlsx) is used or that the elements of the file are documented and preserved alongside a text export of the data.

```{list-table}
:header-rows: 1

* - Preservation Format
  - Requirements
* - Delimited Text (e.g.__.txt__, __.tab__, __csv__)
  - Delimited text is generally the preferred format for the preservation of spreadsheet and database files and is a common export format from many applications. In such files cells are separated by a delimiter and (optionally) a qualifier (e.g. a comma and enclosed in double quotes in .csv files) and rows are represented by new lines. Common delimiters include commas (csv files), tabs or the pipe '~|' character. It is a format that most people are familiar with and has the added advantage that many files (e.g. .csv) will open directly into common applications such as MS Excel. This makes the format ideal for both preservation and dissemination as the file can be easily opened using common software. As highlighted above, this format merely stores the data and additional elements (images, formulae, etc.) should be archived separately (see section below).
* - __.ods__
  - Suitable for long-term preservation of spreadsheet files but embedded graphs or charts should also be stored separately.
* - __.xlsx__
  - Suitable for long-term preservation of spreadsheet files but embedded graphs or charts should also be stored separately.

```

__Checks after Migration__

When migrating files to new formats it is important to carry out a number of checks to ensure that data hasn't become lost or corrupted during the process. Such checks include:

* Check row counts after export
* Check text field lengths i.e. (especially for databases) where the length of the data is the same as the field length it may indicate truncated values.
* Check all sheets or tables have been exported.
* Check any special characters have been preserved.

__Other Formats__

Portable Document Format (preferably .pdfa, see the chapter on [Documents and Digital Texts](https://doi.org/10.5284/b9fa-0259) can occasionally be used to disseminate spreadsheet data. This should only be used where there is significant information present in the form of formatting and layout which can not adequately be replicated in a csv file and is lost when the data is migrated to an XML-based format (ods or xlsx). In some cases it may be necessary to provide a pdf version alongside a csv version for complicated spreadsheets so that users can see what the spreadsheet looked like but can also work with the data.

XML is also widely used for spreadsheets and an application that may become more popular is [Gnumeric](https://gnome.pages.gitlab.gnome.org/gnumeric-web//) part of the GNOME desktop. It is freely available and open source and, as with OpenOffice Calc and Excel, its native file format again is compressed XML.

XML also offers a potentially reliable format for storing database data. A schema (or DTD) would hold the data dictionary which can not be stored so readily and usefully for delimited text files. A number of converters for a variety of database formats are available. Alternatively Table definitions and data can be stored as SQL DDL and DML statements (though users should be aware of variations in SQL dialects).

Another option for databases is the [SIARD](https://www.bar.admin.ch/bar/en/home/archiving/tools/siard-suite.html) database archiving tool (Software Independent Archiving of Relational Databases) which has been partially incorporated into the Planets toolkit. The SIARD Suite is based on international standards such as XML, SQL:1999 and UNICODE and currently supports a number of databases including Oracle, Microsoft SQL Server and Microsoft Access. The Swiss Federal Archives distributes the SIARD Suite free of charge (subject to licence agreement terms).

## 3.3 Metadata and Documentation

Databases and spreadsheets require metadata and documentation at a number of levels to ensure that they can be preserved and reused reliably. The following elements should be recorded and stored with the dataset 

```{list-table}
:header-rows: 1

* - Element
  - Description
* - Project Title
  - 
* - Name of database/spreadsheet file
  -
```
	
Repeat the following section for each worksheet/table within your spreadsheet/database:

```{list-table}
:header-rows: 1

* - Element
  - Description
* - Name of worksheet/table
  -
* - Purpose of worksheet/table
  - 
* - Number of rows of data
  -
* - Primary keys (database only)
  - 
* - Foreign keys (database only)
  -
```

Repeat the following section for each column/field within your spreadsheet/database:

```{list-table}
:header-rows: 1

* - Element
  - Description
* - Field Name
  - Name of database field or spreadsheet column.
* - Field Description
  - Full description of fields and codes or terminology used. Alternatively, codes used within a dataset can be supplied as a separate document.
* - Data type and field length (database only)
  - 
```

The elements above essentially make up the 'data dictionary' commonly associated with databases. In addition, for databases in particular, it is also necessary to describe the relationships between tables either in words or by the inclusion of an entity relationship diagram.

```{figure} ../images/erm.gif
:alt: Figure 1: Example entity relationship diagram.

__Figure 1__: Example entity relationship diagram.
```

Documentation can also include any extra features in the spreadsheet or database that require preservation, for example, formulae, queries, macros, and comments. These can generally be stored alongside the data as text files.

## 3.4 Structuring your data

Although the relationships between files should be clear from the filenames, it is useful to store exported tables or worksheets together under a single directory. Any exported images or documentation can then be stored in sub directories within this structure.