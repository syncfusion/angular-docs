---
layout: post
title: Toolbar
description: Toolbar support
platform: Angular
control: File Explorer
documentation: ug
---

# Toolbar

The toolbar element having the number of tools, and each tool can be configurable. 

## Toolbar items

The toolbar having the list of items to perform various operations and grouped into some categorizes. 

From below you can see the available toolbar items and its categorization:

{% highlight html %}

        // all tools grouped under the below categories

        this.tools: {

                creation: ["NewFolder"],

                navigation: ["Back", "Forward", "Upward"],

                addressBar: ["Addressbar"],

                editing: ["Refresh", "Upload", "Delete", "Rename", "Download"],

                copyPaste: ["Cut", "Copy", "Paste"],

                getProperties: ["Details"],

                searchBar: ["Searchbar"],

                layout: ["Layout"],
                
                sortBy: ["SortBy"]

        },

        // all tools categories are placed in the toolbar by the below order

        this.toolsList: ["layout", "creation", "navigation", "addressBar", "editing", 
        "copyPaste", "sortBy", "getProperties", "searchBar"]

{% endhighlight %}

The following table explains the functionality of each toolbar item:

<table>
<tr>
<th>
Tool name</th><th>
Description</th></tr>
<tr>
<td>
NewFolder <br/><br/></td><td>
It creates a new folder on the current directory.<br/><br/>While click on the NewFolder item, the dialog displays to get the folder name. Based on the user input, FileExplorer creates new folder on the current directory.
Also {{'[createFolder](https://help.syncfusion.com/api/angular/ejfileexplorer#events:createfolder)'| markdownify}} event will be triggered when new folder is created successfully in the file system.<br/><br/><br/><br/></td></tr>
<tr>
<td>
Back <br/><br/></td><td>
It navigates to the previous directory from the user history. When the backward history is not available when it is disabled state.<br/><br/><br/><br/></td></tr>
<tr>
<td>
Forward <br/><br/></td><td>
It navigates to the next directory from the user history. When the forward history is not available when it is disable state.<br/><br/><br/><br/></td></tr>
<tr>
<td>
Upward <br/><br/></td><td>
It navigates to the parent directory of the current folder.<br/><br/><br/><br/></td></tr>
<tr>
<td>
Address bar <br/><br/></td><td>
The Address bar is the textbox which displays the path of the current directory, as a series of its parent directory separated by slash (“/”).<br/><br/>And the address bar is an editable area, so you can enter any directory’s path to a quick navigation.<br/><br/><br/><br/></td></tr>
<tr>
<td>
Refresh <br/><br/></td><td>
It refreshes the current directory.<br/><br/><br/><br/></td></tr>
<tr>
<td>
Upload <br/><br/></td><td>
It uploads a file or list of files into the current directory.<br/><br/>And you can customize the upload configurations, for details check {{'[here](https://help.syncfusion.com/angular/fileexplorer/toolbar#customizing-the-upload-functionality)'| markdownify }}.
<br/><br/><br/><br/></td></tr>
<tr>
<td>
Delete <br/><br/></td><td>
It delete the current selected file or folder. The delete icon is enable state if you select any file or folder.<br/><br/>If you selected the multiple files, it deletes all the selected items.<br/><br/><br/><br/></td></tr>
<tr>
<td>
Rename <br/><br/></td><td>
It delete the current selected file or folder. The delete icon is enable state if you select any file or folder.<br/><br/>
The {{'[remove](https://help.syncfusion.com/api/angular/ejfileexplorer#events:remove)'| markdownify}} event will be triggered when file or folder is deleted.<br/><br/>If you selected the multiple files, it deletes all the selected items.<br/><br/><br/><br/></td></tr>
<tr>
<td>
Download <br/><br/></td><td>
It downloads the selected files. The download icon is enable state if you select any file or folder.<br/><br/>
The {{'[beforeDownload](https://help.syncfusion.com/api/angular/ejfileexplorer#events:beforedownload)'| markdownify}} event will be triggered before the files are downloaded.
<br/><br/>If you select multiple files, it downloads all the files in a zip format.<br/><br/><br/><br/></td></tr>
<tr>
<td>
Cut <br/><br/></td><td>
It makes the copy of the selected files or folders into the clipboard. When the user paste the files in any location, the files are removed from the source location.
The {{'[cut](https://help.syncfusion.com/api/angular/ejfileexplorer#events:cut)'| markdownify}} event will be triggered when files or folders are removed from the source.<br/><br/><br/><br/></td></tr>
<tr>
<td>
Copy <br/><br/></td><td>
It makes the copy of the selected files or folders into the clipboard. When the user paste the files, the copy of the files are pasted in the target location.
The {{'[copy](https://help.syncfusion.com/api/angular/ejfileexplorer#events:copy)'| markdownify}} event will be triggered when file or folder is copied.<br/><br/><br/><br/></td></tr>
<tr>
<td>
Paste <br/><br/></td><td>
It paste the files from the clipboard into the currently selected folder. <br/><br/>Note: when the files are copied into the clipboard, at that time only it enabled.<br/><br/><br/><br/></td></tr>
<tr>
<td>
Details <br/><br/></td><td>
It pastes the files from the clipboard into the currently selected folder. <br/><br/>Note: Only when the files are copied into the clipboard it is enabled.
The {{'[paste](https://help.syncfusion.com/api/angular/ejfileexplorer#events:paste)'| markdownify}} event will be triggered when file or folder is pasted.<br/><br/><br/><br/></td></tr>
<tr>
<td>
Search bar<br/><br/></td><td>
The Search bar is the textbox which is used to search the files from the current directory. It list the files based on the user search.<br/><br/>The search behavior of the Search bar can be customize.<br/><br/><br/><br/></td></tr>
<tr>
<td>Sort By<br/><br/></td>
<td>
It's used to sorting the files and folders from the current directory.The sorting can be done based on the columns available from grid,in both ascending and descending order.<br/><br/>
</td></tr>
</table>


## Toolbar Visibility

The visibility of the toolbar can be customized through the [showToolbar](https://help.syncfusion.com/api/angular/ejfileexplorer#members:showtoolbar) property. By disabling this property you can remove the toolbar from FileExplorer. Also you can remove the particular toolbar item by using [removeToolbarItem](https://help.syncfusion.com/api/angular/ejfileexplorer#methods:removetoolbaritem) method.

{% highlight html %}

<ej-fileexplorer id="fileExplorer" 
   path= "http://js.syncfusion.com/demos/ejServices/Content/FileBrowser/"
   ajaxAction="http://js.syncfusion.com/demos/ejServices/api/FileExplorer/FileOperations" 
   [showToolbar]="false" style="display:block">
</ej-fileexplorer>

{% endhighlight %}

## Toolbar Configuration

As you can see the available toolbar items from [here](#toolbar-items). From the list of available items, you can configure and group your required toolbar items only through the `tools` property. And also you can arrange the toolbar items by the `toolsList` property. 

{% highlight html %}

<ej-fileexplorer id="fileExplorer" 
  path= "http://js.syncfusion.com/demos/ejServices/Content/FileBrowser/"
  ajaxAction="http://js.syncfusion.com/demos/ejServices/api/FileExplorer/FileOperations" 
  [toolsList]="toolsList" [tools]="tools" style="display:block">
</ej-fileexplorer>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'src/fileexplorer/fileexplorer.component.html'
})
export class FileExplorerComponent {
    toolsList: Object;
    tools: Object;
    constructor() {
        this.toolsList =  ["creation", "navigation", "addressBar", "copyPaste", "searchBar"];
        this.tools= {
                    creation: ["NewFolder"],
                    navigation: ["Back", "Forward", "Upward"],
                    addressBar: ["Addressbar"],
                    copyPaste: ["Cut", "Copy", "Paste"],
                    searchBar: ["Searchbar"]
        }
    }
}

{% endhighlight %}

## Search bar  

The Search bar can be customize through the `filterSettings` property. By default the search doesn’t consider the case sensitivity, and the search works based on filter type.

The FileExplorer allows the following filter types in the search functionality.

* Starts with
* Contains
* Ends with

So you can configure the filter type with case sensitivity like below:

{% highlight html %}

<ej-fileexplorer id="fileExplorer" 
  path= "http://js.syncfusion.com/demos/ejServices/Content/FileBrowser/"
  ajaxAction="http://js.syncfusion.com/demos/ejServices/api/FileExplorer/FileOperations" 
  [filterSettings]="filterSettings" style="display:block">
</ej-fileexplorer>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'src/fileexplorer/fileexplorer.component.html'
})
export class FileExplorerComponent {
    filterSettings: Object;
    constructor() {
        this.filterSettings= {
                    // it enables the case sensitive search
                    caseSensitiveSearch: true,
                    // it changes the search filter type as “startswith”
                    filterType: ej.FileExplorer.filterType.EndsWith
    }    
    ej.FileExplorer.filterType = {

            /**  Supports to search text with startswith  */

            StartsWith: "startswith",

            /**  Supports to search text with contains */

            Contains: "contains",

            /**  Supports to search text with endswith */

            EndsWith: "endswith",

    };
    }
}

{% endhighlight %}

## Custom Tool in Toolbar

From the [toolbar items](#toolbar-items) you can see the list of built-in tools to perform the operations. Along with this built-in tools, you can add your custom tool with the custom functionality.

{% highlight html %}

<ej-fileexplorer id="fileExplorer" 
   path= "http://js.syncfusion.com/demos/ejServices/Content/FileBrowser/"
   ajaxAction="http://js.syncfusion.com/demos/ejServices/api/FileExplorer/FileOperations" 
   [toolsList]="toolsList" [tools]="tools" style="display:block">
</ej-fileexplorer>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'src/fileexplorer/fileexplorer.component.html'
})
export class FileExplorerComponent {
    toolsList: Object;
    tools: Object;
    constructor() {
    this.toolsList= ["creation", "navigation", "addressBar", "copyPaste", 
    "searchBar", "customTool"];
    // defines the tool items for customTool category 
    this.tools= {
        customTool: [{
            name: "Help",
            tooltip: "Help ",
            css: "e-fileExplorer-toolbar-icon Help",
            action: function () {
                // handle the click handler of custom tool 
                alert("custom tool item clicked");
            }
        }]
    }
    }
}

{% endhighlight %}


Define the CSS that needs to apply for the custom tool.

{% highlight css %}

        .e-fileExplorer-toolbar-icon {
            height: 22px;
            width: 22px;
            font-family: 'ej-webfont';
            font-size: 18px;
            margin-top: 2px;
            text-align: center;
        }

        .e-fileExplorer-toolbar-icon.Help:before {
            content: "\e72b";
        }

{% endhighlight %}

## Enable / Disable the Toolbar Item

Each toolbar item can be enabled or disabled through the below client-side public methods.

* enableToolbarItem
* disableToolbarItem

These methods accepts the tool name as the parameter. It also allows the parameter as tool item index or the jQuery object of the tool item. 

{% highlight javascript %}


var fileExpObj = $("#fileExplorer").data("ejFileExplorer");

// this disables the NewFolder item

fileExpObj.disableToolbarItem("NewFolder");

// this also disables the NewFolder item (since index of NewFolder is 0)

fileExpObj.disableToolbarItem(0);



// this enables the NewFolder item

fileExpObj.enableToolbarItem("NewFolder");


{% endhighlight %}

### Enable / Disable the custom added tool in Toolbar Item

If you want to enable / disable the custom added tool in toolbar, you need to pass the corresponding li elements of custom added tool in [enableToolbarItem](https://help.syncfusion.com/api/js/ejfileexplorer#methods:enabletoolbaritem) / [disableToolbarItem](https://help.syncfusion.com/api/js/ejfileexplorer#methods:disabletoolbaritem) method of FileExplorer. Since we have consider this custom tool as a object type.

{% highlight javascript %}
        
        var fileExpObj = $("#fileExplorer").data("ejFileExplorer");
        
        //tool is a cssClass of FileExplorer 
        // this disables the custom tool item 
        
        var li = $(".tool").find(".Help").closest('li'); 
        fileExpObj.disableToolbarItem(li); 
        
        // this enables the custom tool item 
        fileExpObj.enableToolbarItem(li);

{% endhighlight %}

## Customizing the Upload Functionality

FileExplorer helps you to upload the file using Upload component. File upload can be done through the toolbar item or context menu item. The `uploadSettings` property is used to configure the upload functionalities.

This property has the below sub properties with the default values:

{% highlight javascript %}

        uploadSettings: {

                allowMultipleFile: true,

                maxFileSize: 31457280,

                autoUpload: false

        }

{% endhighlight %}

**allowMultipleFile**: This property used to control the behavior of multiple files upload and this was enabled by default so you can upload multiple files at a time. If you disable this `allowMultipleFile` property then you can upload only one file at a time.

**maxFileSize**: The property limits the maximum file size to upload. It accepts the value in bytes.

**autoUpload**: when you enable this property,  the upload action performed automatically after select the files. When you disable this property, it shows a confirmation dialog with the selected file details and perform the upload action on press the “upload” button. 

During upload process following events will be triggered, {{'[beforeUploadSend](https://help.syncfusion.com/api/angular/ejfileexplorer#events:beforeuploadsend)'| markdownify}}, {{'[beforeUploadDialogOpen](https://help.syncfusion.com/api/angular/ejfileexplorer#events:beforeuploaddialogopen)'| markdownify}}, {{'[beforeUpload](https://help.syncfusion.com/api/angular/ejfileexplorer#events:beforeupload)'| markdownify}}, {{'[uploadError](https://help.syncfusion.com/api/angular/ejfileexplorer#events:uploaderror)'| markdownify}}, {{'[uploadSuccess](https://help.syncfusion.com/api/angular/ejfileexplorer#events:uploadsuccess)'| markdownify}} and {{'[uploadComplete](https://help.syncfusion.com/api/angular/ejfileexplorer#events:uploadcomplete)'| markdownify}}. You can customize the upload settings with these events.

{% highlight html %}

<ej-fileexplorer id="fileExplorer" 
   path= "http://js.syncfusion.com/demos/ejServices/Content/FileBrowser/"
   ajaxAction="http://js.syncfusion.com/demos/ejServices/api/FileExplorer/FileOperations"
   [uploadSettings]="uploadSettings" style="display:block">
</ej-fileexplorer>

{% endhighlight %}



{% highlight html %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'src/fileexplorer/fileexplorer.component.html'
})
export class FileExplorerComponent {
    uploadSettings: Object;
    tools: Object;
    constructor() {
    this.uploadSettings= {
    // it disables the multi file upload functionality
    allowMultipleFile: false,
    // it enables the auto upload functionality
    autoUpload: true
    }
    }
}

{% endhighlight %}