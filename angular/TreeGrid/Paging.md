---
layout: post
title: Paging
description: paging
platform: Angular
control: TreeGrid
documentation: ug
api: /api/js/ejtreegrid
---

# Paging

The TreeGrid control provides support for displaying records in paginated view. Paging can be enabled in TreeGrid by setting the `allowPaging` property as `true`.

The below code snippet explains enabling paging in TreeGrid.

{% highlight javascript %}

<ej-treegrid id="TreeGridControl" [allowPaging]="true"
    //...>
</ej-treegrid>

{% endhighlight %}

The output of the TreeGrid with paging enabled is displayed below

![](Paging_images/Paging_img1.png)

## Paging settings

The paging in TreeGrid can be customized by using `pageSettings` property.
The number of records to be displayed per page can be limited by using the `pageSettings.pageSize` property. 
The number of root nodes or the 0th level records to be displayed per page can be limited by setting the `pageSettings.pageSizeMode` property as `Root`. When pageSettings.pageSizeMode property is set as `Root` the number of records to displayed per page which is defined in the `pageSettings.pageSize` property will be considered only for the root nodes or the 0th level records.
`pageSettings.pageCount` property is used to display the page number to be displayed in the pager.
`pageSettings.currentPage` property is used to set the active page to displayed initially.
`pageSettings.totalRecordsCount` property is used to limit the total number of records from the data source to be displayed in TreeGrid.
 The following code example explains the properties in pageSettings. 

{% highlight javascript %}

<ej-treegrid id="TreeGridControl" [pageSettings]="pageSettings" [allowPaging]="true"
    //...>
</ej-treegrid>

{% endhighlight %}

{% highlight javascript %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
    templateUrl: 'app/app.component.html'
})
export class AppComponent {
  public pageSettings:any;    
  constructor() {
   //...
   this.pageSettings={
             pageCount: 5,
        currentPage: 3,
        totalRecordsCount: 50,
        pageSizeMode: "all",
        pageSize: "12",
        }
  }
}

{% endhighlight %}

You can also find the demo for pageSettings [here](http://js.syncfusion.com/demos/web/#!/bootstrap/treegrid/paging/pagingapi)

## Pager Template

It is possible to customize the default pager in TreeGrid by using the `pageSettings.template` property.
The below code snippet explains how to customize the default pager with template

{% highlight html %}
<script type="text/x-jsrender" id="template">
    <div class="e-pagercontainer">
        <div class="e-first e-icon e-mediaback e-firstpagedisabled e-disable" title="Go to first page"></div>
        <div class="e-prev e-icon e-arrowheadleft-2x e-prevpagedisabled e-disable" style="border-right:none" title="Go to previous page"></div>
    </div>
    <div class="e-pagercontainer e-currentPageContainer" style="border-radius:0px">
        <input id="currentPage" class="e-pagercontainer" type="text" style="text-align:center; margin:0px;border:none;width:32px;height:23px" />
    </div>
    <div id="totalPages" class="e-pagercontainer" style="margin-left: 2px;margin-bottom:5px;border: none; ">
        <span></span>
    </div>
    <div class="e-pagercontainer">
        <div class="e-nextpage e-icon e-arrowheadright-2x e-default" title="Go to next page"></div>
        <div class="e-lastpage e-icon e-mediaforward e-default" title="Go to last page"></div>
    </div>
</script> 

{% endhighlight %}

Write the below css code in app.component.css file
{% highlight css %}
    #currentPage {
        background-color: white;
    }

    .e-currentPageContainer {
        border-bottom: 1px solid #e0e0e0!important;
    }

    .e-pagercontainer .e-icon {
        display: inline-block;
        height: 8px;
    }

    .e-pager .e-pagercontainer {
        margin: 0px;
        margin-left: 6px;
    }
{% endhighlight %}

{% highlight javascript %}

<ej-treegrid id="TreeGridControl" [pageSettings]="pageSettings" [allowPaging]="true"
    //...>
</ej-treegrid>

{% endhighlight %}

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html',
    styleUrls: ['app/app.component.css']
})
export class AppComponent {
    public pageSettings: any;

    constructor() {
        //...
        this.pageSettings = {
            template: "#template",
        }
    }
}

{% endhighlight %}

You can also find the demo for TreeGrid with pager template [here](http://js.syncfusion.com/demos/web/#!/bootstrap/treegrid/paging/pagertemplate)

The below image displays TreeGrid with paging template.
![](Paging_images/Paging_img3.png)

## Paging - Touch Option

With paging and responsive mode enabled in TreeGrid, it is possible to change the current page using swipe action.

The following code example describes how to enable multiple selection in TreeGrid.	


{% highlight javascript %}

<ej-treegrid id="TreeGridControl" [isResponsive]="true" [allowPaging]="true"
    //...>
</ej-treegrid>

{% endhighlight %}
