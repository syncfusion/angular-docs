---
layout: post
title: Behavior Settings
description: Customize the behavior of FileExplorer.
platform: Angular
control: FileExplorer
documentation: ug
---

# Behavior Settings

Here are the some properties to customize the behavior of FileExplorer.

## File type restriction

FileExplorer control showcase all the files from the filesystem, here you can customize the file types that what you want to show by using `fileTypes` property. It filter the files based on the files extensions.

By default it having the value “*.*”, so it allows all the file types. In case of image browser you can allow the image files only by setting "*.png, *.gif, *.jpg, *.jpeg", so it doesn’t allow the other type of files.

{% highlight html %}

<ej-fileexplorer id="fileExplorer" 
  path= "http://js.syncfusion.com/demos/ejServices/Content/FileBrowser/"
  ajaxAction="http://js.syncfusion.com/demos/ejServices/api/FileExplorer/FileOperations" 
  width="100%" minWidth="150px" fileTypes="*.png, *.gif, *.jpg, *.jpeg" layout= "tile" 
  style="display:block">
</ej-fileexplorer>

{% endhighlight %}

## Customize the AJAX request settings

As you already know FileExplorer is a client – server based control and each action performed in the client sends an AJAX request to the server to perform the server side operations. While the AJAX request, the AJAX configurations can be customized through `ajaxSettings` property.

The [beforeAjaxRequest](https://help.syncfusion.com/api/angular/ejfileexplorer#events:beforeajaxrequest) event will be triggered before the AJAX request is performed. You can modify the ajax request in this event.

You can see the following requests passed during the **client – server actions**:

* Read, 
* Create folder
* Remove
* Rename
* Paste
* Get details
* Upload
* Download 
* Get Image

The following is the syntax for ajaxSettings property.

{% highlight javascript %}

       ajaxSettings: { read: {}, createFolder: {}, remove: {}, rename: {}, paste: {}, getDetails: {}, upload: {}, download: {}, getImage: {} }
                
{% endhighlight %}

The actions “read, createFolder, remove, rename, paste, getDetails” are supported all the jQuery AJAX configurations. The remaining actions “upload, download, getImage” are accepted the URL only.

If you want to customize read action alone, the AJAX **url** and **dataType** are changed for the read action, refer the below code example.

{% highlight html %}

<ej-fileexplorer id="fileExplorer" 
    path= "http://js.syncfusion.com/demos/ejServices/Content/FileBrowser/"
    ajaxAction="http://js.syncfusion.com/demos/ejServices/api/FileExplorer/FileOperations" 
    [ajaxSettings]="ajaxSettings" style="display:block">
</ej-fileexplorer>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'src/fileexplorer/fileexplorer.component.html'
})
export class FileExplorerComponent {
    ajaxSettings: Object;
    constructor() {
        let ajaxJSONPActionHandler = "http://js.syncfusion.com/demos/ejServices/api/FileExplorer/FileOperationsCors";
        this.ajaxSettings={
            read: {
                url: ajaxJSONPActionHandler,
                dataType: "jsonp"
            }
        };
    }
}

{% endhighlight %}

For following file actions, you have to make the custom request in URL format only, not able to use jQuery AJAX configurations as like "dataType", "contentType", "async", etc..

* upload
* download 
* getImage

Also its compulsory to add "{0}" in the end of "upload, download and getImage" URL's. That helps to pass the internal parameters with the action request.

{% highlight javascript %}

       this.ajaxSettings: {
            upload: {
                url: ajaxActionHandler + "/upload{0}"
            },
            download: {
                url: ajaxActionHandler + "/download{0}"
            },
            getImage: {
                url: ajaxActionHandler + "/getImage{0}"
            }
      }
                
{% endhighlight %}

N> **ajaxActionHandler** - prefix URL of AJAX handling method
