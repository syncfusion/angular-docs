---
layout: post
title: Service reference for ejTreeGrid widget
description: What are the exporting services used in Essential JavaScript TreeGrid.
documentation: api
platform: Angular
keywords: ejTreeGrid, Services, Essential JS TreeGrid, TreeGrid, Excel Exporting Service, TreeGrid Exporting
metaname: 
metacontent:
control: ejTreeGrid
api: /api/js/ejtreegrid
---
# TreeGrid Exporting services

## Description

The following are the types of exporting is available in TreeGrid.

* PDF Export.
* Excel Export.

## PDF Export

### URL

[http://js.syncfusion.com/demos/ejServices/api/JSTreeGridExport/PdfExport](http://js.syncfusion.com/demos/ejServices/api/JSTreeGridExport/PdfExport)

### Parameter

Type1:

<table>
<tr>
<td>
Name</td><td>
Type</td><td>
Description</td></tr>
<tr>
<td>
TreeGridProperties</td><td>
Object</td><td>
It takes TreeGrid model properties that should be pass to exporting</td></tr>
<tr>
<td>
datasource</td><td>
object</td><td>
It holds the data to be exported in PDF</td></tr>
<tr>
<td>
TreeGridExportSettings</td><td>
object</td><td>
Returns the exporting settings like Unicode support, columns fit to width, hidden column, template, etc..</td></tr>
</table>

Type2:

<table>
<tr>
<td>
Name</td><td>
Type</td><td>
Description</td></tr>
<tr>
<td>
TreeGridProperties</td><td>
Object</td><td>
It takes TreeGrid model properties that should be pass to exporting</td></tr>
<tr>
<td>
datasource</td><td>
object</td><td>
It holds the data to be exported in PDF</td></tr>
<tr>
<td>
TreeGridExportSettings</td><td>
object</td><td>
Returns the exporting settings like Unicode support, columns fit to width, hidden column, template, etc..</td></tr>
<tr>
<td>
fileName</td><td>
String</td><td>
With this parameter you can set the downloaded file name. By default it is set to “Export”</td></tr>
</table>

Type3:

<table>
<tr>
<td>
Name</td><td>
Type</td><td>
Description</td></tr>
<tr>
<td>
TreeGridProperties</td><td>
Object</td><td>
It takes TreeGrid model properties that should be pass to exporting</td></tr>
<tr>
<td>
datasource</td><td>
object</td><td>
It holds the data to be exported in PDF</td></tr>
<tr>
<td>
TreeGridExportSettings</td><td>
object</td><td>
Returns the exporting settings like Unicode support, columns fit to width, hidden column, template, etc..</td></tr>
<tr>
<td>
fileName</td><td>
String</td><td>
With this parameter you can set the downloaded file name. By default it is set to “Export”</td></tr>
<tr>
<td>
filePath</td><td>
String</td><td>
With this parameter you can set the location where the exporting file should downloaded. It can be local or server machine file path.</td></tr>
</table>

Type4:

<table>
<tr>
<td>
Name</td><td>
Type</td><td>
Description</td></tr>
<tr>
<td>
TreeGridProperties</td><td>
Object</td><td>
It takes TreeGrid model properties that should be pass to exporting</td></tr>
<tr>
<td>
datasource</td><td>
object</td><td>
It holds the data to be exported in PDF</td></tr>
<tr>
<td>
TreeGridExportSettings</td><td>
object</td><td>
Returns the exporting settings like Unicode support, columns fit to width, hidden column, template, etc..</td></tr>
<tr>
<td>
exportToFile </td><td>
Boolean</td><td>
Is a Boolean argument, and value ‘true’ specifies the exporting is completed and download it, value ‘false’ specifies the export TreeGrid internally and append something else to it before download starts.</td></tr>
<tr>
<td>
headerText</td><td>
String</td><td>
HeaderText Is to specify the title for export document.</td></tr>
</table>
<table>
<tr>
<td>
Name</td><td>
Type</td><td>
Description</td></tr>
<tr>
<td>
TreeGridProperties</td><td>
Object</td><td>
It takes TreeGrid model properties that should be pass to exporting</td></tr>
<tr>
<td>
datasource</td><td>
object</td><td>
It holds the data to be exported in PDF</td></tr>
<tr>
<td>
TreeGridExportSettings</td><td>
object</td><td>
Returns the exporting settings like Unicode support, columns fit to width, hidden column, template, etc..</td></tr>
<tr>
<td>
fileName</td><td>
String</td><td>
With this parameter you can set the downloaded file name. By default it is set to “Export”</td></tr>
<tr>
<td>
exportToFile </td><td>
Boolean</td><td>
Is a Boolean argument, and value ‘true’ specifies the exporting is completed and download it, value ‘false’ specifies the export TreeGrid internally and append something else to it before download starts.</td></tr>
<tr>
<td>
headerText</td><td>
String</td><td>
HeaderText Is to specify the title for export document.</td></tr>
</table>

Type5:

<table>
<tr>
<td>
Name</td><td>
Type</td><td>
Description</td></tr>
<tr>
<td>
TreeGridProperties</td><td>
Object</td><td>
It takes TreeGrid model properties that should be pass to exporting</td></tr>
<tr>
<td>
datasource</td><td>
object</td><td>
It holds the data to be exported in PDF</td></tr>
<tr>
<td>
TreeGridExportSettings</td><td>
object</td><td>
Returns the exporting settings like Unicode support, columns fit to width, hidden column, template, etc..</td></tr>
<tr>
<td>
fileName</td><td>
String</td><td>
With this parameter you can set the downloaded file name. By default it is set to “Export”</td></tr>
<tr>
<td>
exportToFile </td><td>
Boolean</td><td>
Is a Boolean argument, and value ‘true’ specifies the exporting is completed and download it, value ‘false’ specifies the export TreeGrid internally and append something else to it before download starts.</td></tr>
<tr>
<td>
headerText</td><td>
String</td><td>
HeaderText Is to specify the title for export document.</td></tr>
</table>

Type6:

<table>
<tr>
<td>
Name</td><td>
Type</td><td>
Description</td></tr>
<tr>
<td>
TreeGridProperties</td><td>
Object</td><td>
It takes TreeGrid model properties that should be pass to exporting</td></tr>
<tr>
<td>
datasource</td><td>
object</td><td>
It holds the data to be exported in PDF</td></tr>
<tr>
<td>
TreeGridExportSettings</td><td>
object</td><td>
Returns the exporting settings like Unicode support, columns fit to width, hidden column, template, etc..</td></tr>
<tr>
<td>
fileName</td><td>
String</td><td>
With this parameter you can set the downloaded file name. By default it is set to “Export”</td></tr>
<tr>
<td>
filePath</td><td>
String</td><td>
With this parameter you can set the location where the exporting file should downloaded. It can be local or server machine file path.</td></tr>
<tr>
<td>
exportToFile </td><td>
Boolean</td><td>
Is a Boolean argument, and value ‘true’ specifies the exporting is completed and download it, value ‘false’ specifies the export TreeGrid internally and append something else to it before download starts.</td></tr>
<tr>
<td>
headerText</td><td>
String</td><td>
HeaderText Is to specify the title for export document.</td></tr>
</table>

Type7:

<table>
<tr>
<td>
Name</td><td>
Type</td><td>
Description</td></tr>
<tr>
<td>
TreeGridProperties</td><td>
Object</td><td>
It takes TreeGrid model properties that should be pass to exporting</td></tr>
<tr>
<td>
datasource</td><td>
object</td><td>
It holds the data to be exported in PDF</td></tr>
<tr>
<td>
TreeGridExportSettings</td><td>
object</td><td>
Returns the exporting settings like Unicode support, columns fit to width, hidden column, template, etc..</td></tr>
<tr>
<td>
Document</td><td>
Object</td><td>
It specifies in case of multiple exporting, in which document the file export should append, it holds the internally stored PDF files which is exported previously.</td></tr>
<tr>
<td>
exportToFile </td><td>
Boolean</td><td>
Is a Boolean argument, and value ‘true’ specifies the exporting is completed and download it, value ‘false’ specifies the export TreeGrid internally and append something else to it before download starts.</td></tr>
<tr>
<td>
headerText</td><td>
String</td><td>
HeaderText Is to specify the title for export document.</td></tr>
</table>

Type8:

<table>
<tr>
<td>
Name</td><td>
Type</td><td>
Description</td></tr>
<tr>
<td>
TreeGridProperties</td><td>
Object</td><td>
It takes TreeGrid model properties that should be pass to exporting</td></tr>
<tr>
<td>
datasource</td><td>
object</td><td>
It holds the data to be exported in PDF</td></tr>
<tr>
<td>
TreeGridExportSettings</td><td>
object</td><td>
Returns the exporting settings like Unicode support, columns fit to width, hidden column, template, etc..</td></tr>
<tr>
<td>
Filename</td><td>
string</td><td>
With this parameter you can set the downloaded file name. By default it is set to “Export”.</td></tr>
<tr>
<td>
Document</td><td>
Object</td><td>
It specifies in case of multiple exporting, in which document the file export should append, it holds the internally stored PDF files which is exported previously.</td></tr>
<tr>
<td>
exportToFile </td><td>
Boolean</td><td>
Is a Boolean argument, and value ‘true’ specifies the exporting is completed and download it, value ‘false’ specifies the export TreeGrid internally and append something else to it before download starts.</td></tr>
<tr>
<td>
headerText</td><td>
String</td><td>
HeaderText Is to specify the title for export document.</td></tr>
</table>

Type9:

<table>
<tr>
<td>
Name</td><td>
Type</td><td>
Description</td></tr>
<tr>
<td>
TreeGridProperties</td><td>
Object</td><td>
It takes TreeGrid model properties that should be pass to exporting</td></tr>
<tr>
<td>
datasource</td><td>
object</td><td>
It holds the data to be exported in PDF</td></tr>
<tr>
<td>
TreeGridExportSettings</td><td>
object</td><td>
Returns the exporting settings like Unicode support, columns fit to width, hidden column, template, etc..</td></tr>
<tr>
<td>
Filename</td><td>
string</td><td>
With this parameter you can set the downloaded file name. By default it is set to “Export”.</td></tr>
<tr>
<td>
filePath</td><td>
String</td><td>
With this parameter you can set the location where the exporting file should downloaded. It can be local or server machine file path.</td></tr>
<tr>
<td>
Document</td><td>
Object</td><td>
It specifies in case of multiple exporting, in which document the file export should append, it holds the internally stored PDF files which is exported previously.</td></tr>
<tr>
<td>
exportToFile </td><td>
Boolean</td><td>
Is a Boolean argument, and value ‘true’ specifies the exporting is completed and download it, value ‘false’ specifies the export TreeGrid internally and append something else to it before download starts.</td></tr>
<tr>
<td>
headerText</td><td>
String</td><td>
HeaderText Is to specify the title for export document.</td></tr>
</table>

### Request

{% highlight javascript %}

<ej-treegrid id="TreeGridControl" (toolbarClick)="toolbarClick($event)"
    //...>
</ej-treegrid>

{% endhighlight %}

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html'
})
export class AppComponent {
    public contextMenuSettings: any;

    constructor() {
        //...
        this.contextMenuSettings = {
            showContextMenu: true
            contextMenuItems: ["add", "edit", "delete"]
        }
    }
    toolbarClick(sender) {
        var TreeGridObj = $("#TreeGridControl").data("ejTreeGrid");
        TreeGridObj.exportGrid = TreeGridObj["export"];

        if (sender.itemName == "PDF Export") {
            TreeGridObj.exportGrid('http://js.syncfusion.com/ejServices/api/JSTreeGridExport/PdfExport/api/JSTreeGridExport/PdfExport', "", false);

            sender.cancel = true;
        }
    }
}

{% endhighlight %}

Following example will take part in the project service

~~~csharp

public void PdfExport()

{

string gridModel = HttpContext.Current.Request.Params["TreeGridModel"];

TreeGridProperties gridProperty = ConvertGridObject(gridModel);

PdfExport exp = new PdfExport();

TaskDetailsCollection tc = new TaskDetailsCollection();

IEnumerable<TaskDetails> result = tc.GetDataSource(); // datasource to be exported

TreeGridExportSettings settings = new TreeGridExportSettings();

settings.Theme = ExportTheme.FlatAzure;

exp.Export(gridProperty, result, settings, "Export");

}

~~~

## Excel export

### URL

[http://js.syncfusion.com/ejServices/api/JSTreeGridExport/ExcelExport](http://js.syncfusion.com/ejServices/api/JSTreeGridExport/ExcelExport)

### Parameter

Type1:

<table>
<tr>
<td>
Name</td><td>
Type</td><td>
Description</td></tr>
<tr>
<td>
TreeGridProperties</td><td>
Object</td><td>
It takes TreeGrid model properties that should be pass to exporting</td></tr>
<tr>
<td>
datasource</td><td>
object</td><td>
It holds the data to be exported in PDF</td></tr>
<tr>
<td>
excelName</td><td>
String</td><td>
It specifies the file extension to be downloaded</td></tr>
<tr>
<td>
excelVersion</td><td>
String</td><td>
Excel version in which document should download</td></tr>
<tr>
<td>
TreeGridExportSettings</td><td>
object</td><td>
Returns the exporting settings like Unicode support, columns fit to width, hidden column, template, etc..</td></tr>
</table>

Type2:

<table>
<tr>
<td>
Name</td><td>
Type</td><td>
Description</td></tr>
<tr>
<td>
TreeGridProperties</td><td>
Object</td><td>
It takes TreeGrid model properties that should be pass to exporting</td></tr>
<tr>
<td>
datasource</td><td>
object</td><td>
It holds the data to be exported in PDF</td></tr>
<tr>
<td>
excelName</td><td>
String</td><td>
It specifies the file extension to be downloaded</td></tr>
<tr>
<td>
excelVersion</td><td>
String</td><td>
Excel version in which document should download</td></tr>
<tr>
<td>
TreeGridExportSettings</td><td>
object</td><td>
Returns the exporting settings like Unicode support, columns fit to width, hidden column, template, etc..</td></tr>
<tr>
<td>
fileName</td><td>
String</td><td>
With this parameter you can set the downloaded file name. By default it is set to “ExcelExport”</td></tr>
</table>

Type3:

<table>
<tr>
<td>
Name</td><td>
Type</td><td>
Description</td></tr>
<tr>
<td>
TreeGridProperties</td><td>
Object</td><td>
It takes TreeGrid model properties that should be pass to exporting</td></tr>
<tr>
<td>
datasource</td><td>
object</td><td>
It holds the data to be exported in PDF</td></tr>
<tr>
<td>
excelName</td><td>
String</td><td>
It specifies the file extension to be downloaded</td></tr>
<tr>
<td>
excelVersion</td><td>
String</td><td>
Excel version in which document should download</td></tr>
<tr>
<td>
TreeGridExportSettings</td><td>
object</td><td>
Returns the exporting settings like Unicode support, columns fit to width, hidden column, template, etc..</td></tr>
<tr>
<td>
isLocalSave</td><td>
Boolean</td><td>
It specifies the file have to save locally or can export directly in case of multiple export.</td></tr>
<tr>
<td>
filePath</td><td>
String</td><td>
With this parameter you can set the location where the exporting file should downloaded. It can be local or server machine file path.</td></tr>
</table>

### Request 

{% highlight javascript %}

<ej-treegrid id="TreeGridControl" (toolbarClick)="toolbarClick($event)"
    //...>
</ej-treegrid>

{% endhighlight %}

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html'
})
export class AppComponent {
    public contextMenuSettings: any;

    constructor() {
        //...
        this.contextMenuSettings = {
            showContextMenu: true
            contextMenuItems: ["add", "edit", "delete"]
        }
    }
    toolbarClick(sender) {
        var TreeGridObj = $("#TreeGridControl").data("ejTreeGrid");
        TreeGridObj.exportGrid = TreeGridObj["export"];

        if (sender.itemName == "Excel Export") {
            TreeGridObj.exportGrid('http://js.syncfusion.com/ejServices/api/JSTreeGridExport/ExcelExport', "", false);
            sender.cancel = true;
        }
    }
}

{% endhighlight %}

Following example will take part in the project service

~~~csharp

public void ExcelExport()

{

string gridModel = HttpContext.Current.Request.Params["TreeGridModel"];

TreeGridProperties gridProperty = ConvertGridObject(gridModel);

ExcelExport exp = new ExcelExport();

TaskDetailsCollection tc = new TaskDetailsCollection();

IEnumerable<TaskDetails> result = tc.GetDataSource();

exp.Export(gridProperty, result, "ExcelExport.xlsx", ExcelVersion.Excel2010, new TreeGridExportSettings() { Theme = ExportTheme.FlatAzure });

}

~~~

