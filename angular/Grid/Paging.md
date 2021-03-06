---
layout: post
title: Paging with Grid widget for Syncfusion Essential JS
description: How to enable paging and its functionalites.
platform: js
control: Grid
documentation: ug
api: /api/js/ejgrid
--- 
# Paging

You can display the grid records in paged view, by setting [`allowPaging`](https://help.syncfusion.com/api/angular/ejgrid#members:allowpaging "allowPaging") property as `true`. 

The code snippet to enable paging is follows.

{% highlight html %}
<ej-grid id="Grid" [dataSource]="gridData" [allowPaging]="true">
    <e-columns>
        <e-column field="OrderID"></e-column>
        <e-column field="EmployeeID"></e-column>
        <e-column field="CustomerID"></e-column>
        <e-column field="ShipCountry"></e-column>
        <e-column field="Freight"></e-column>
    </e-columns>
</ej-grid>
{% endhighlight %}

{% highlight javascript %}
import {Component, ViewEncapsulation} from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
})
export class AppComponent {
    public gridData;
    constructor()
    {
        //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
        this.gridData = window.gridData;
    }
}
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](paging_images/paging_img1.png)


## Pager with query string

You can pass the current page information as a query string while navigating to other page. To enable query string, set the [`enableQueryString`](https://help.syncfusion.com/api/angular/ejgrid#members:pagesettings-enablequerystring "enableQueryString") property of [`pageSettings`](https://help.syncfusion.com/api/angular/ejgrid#members:pagesettings "pageSettings") as `true`.

The following code example describes the above behavior.

{% highlight html %}
<ej-grid id="Grid" [dataSource]="gridData" [allowPaging]="true" [pageSettings]="pageSettings">
    <e-columns>
        <e-column field="OrderID"></e-column>
        <e-column field="EmployeeID"></e-column>
        <e-column field="CustomerID"></e-column>
        <e-column field="ShipCountry"></e-column>
        <e-column field="Freight"></e-column>
    </e-columns>
</ej-grid>
{% endhighlight %}

{% highlight javascript %}
import {Component, ViewEncapsulation} from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
})
export class AppComponent {
    public gridData;
    public pageSettings;
    constructor()
    {
        //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
        this.gridData = window.gridData;
        this.pageSettings = { enableQueryString: true };
    }
}
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](paging_images/paging_img2.png)


## Pager template

Apart from default pager, there is an option to render a specific custom template in a grid pager. To render template in pager, set [`enableTemplates`](https://help.syncfusion.com/api/angular/ejgrid#members:pagesettings-enabletemplates "enableTemplates") as true and [`template`](https://help.syncfusion.com/api/angular/ejgrid#members:pagesettings-template "template") properties of [`pageSettings`](https://help.syncfusion.com/api/angular/ejgrid#members:pagesettings "pageSettings").

Prevent to show the default pager while enabling the pager [`template`](https://help.syncfusion.com/api/angular/ejgrid#members:pagesettings-template "template") by setting [`showDefaults`](https://help.syncfusion.com/api/angular/ejgrid#members:pagesettings-showdefaults "showDefaults") property of [`pageSettings`](https://help.syncfusion.com/api/angular/ejgrid#members:pagesettings "pageSettings") as `false`.

N> It's a standard way to enclose the [`template`](https://help.syncfusion.com/api/angular/ejgrid#members:pagesettings-template "template") within the `script` tag with `type` as "text/x-jsrender".

The following code example describes the above behavior.

{% highlight html %}
<ej-grid id="Grid" #Grid [dataSource]="gridData" [allowPaging]="true" [pageSettings]="pageSettings" (create)="onCreate($event)">
    <e-columns>
        <e-column field="OrderID"></e-column>
        <e-column field="EmployeeID"></e-column>
        <e-column field="CustomerID"></e-column>
        <e-column field="ShipCountry"></e-column>
        <e-column field="Freight"></e-column>
    </e-columns>
</ej-grid>
{% endhighlight %}

{% highlight css %}
.e-grid .e-pager .e-pagercontainer {
	border-width: 0px;
	overflow: visible;
}
{% endhighlight %}

{% highlight javascript %}
import {Component, ViewEncapsulation} from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
})
export class AppComponent {
    @ViewChild('Grid') Grid: EJComponents<any, any>;
    public gridData;
    public pageSettings;
    constructor()
    {
        //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
        this.gridData = window.gridData;
        this.pageSettings = { enableTemplates: true, template: "#template", showDefaults: false };
    }
}
onCreate(args:any){
    $("#btn").ejButton({
        click : function(e){
            var val = $("#currentPage").val();
            var gridObj = this.Grid.widget;
            gridObj.gotoPage(val);
        }
    });
}
{% endhighlight %}

Place the template inside index.html file
{% highlight html %}
<script id="template" type="text/x-jsrender">
<input id="currentPage" type="text" style="text-align: center; width: 32px; height: 21px; background: white;" value="1" />
<label>of 200</label>
<button id="btn">Go to</button>
</script>
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](paging_images/paging_img3.png)


## Pager with pageSize drop down

There is an option to set the size of page by means selecting the pageSize you wish from the options available at the dropdown in pager. To render drop down in pager, provide the pageSize values you wish to display in drop down as `array` values to [`pageSizeList`](https://help.syncfusion.com/api/angular/ejgrid#members:pagesettings-pagesizelist "pageSizeList") property of [`pageSettings`](https://help.syncfusion.com/api/angular/ejgrid#members:pagesettings "pageSettings").

The following code example describes the above behavior.

{% highlight html %}
<ej-grid id="Grid" #Grid [dataSource]="gridData" [allowPaging]="true" [pageSettings]="pageSettings">
    <e-columns>
        <e-column field="OrderID"></e-column>
        <e-column field="EmployeeID"></e-column>
        <e-column field="CustomerID"></e-column>
        <e-column field="ShipCountry"></e-column>
        <e-column field="Freight"></e-column>
    </e-columns>
</ej-grid>
{% endhighlight %}

{% highlight javascript %}
import {Component, ViewEncapsulation} from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
})
export class AppComponent {
    public gridData;
    public pageSettings;
    constructor()
    {
        //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
        this.gridData = window.gridData;
        this.pageSettings = { pageSize: 14, pageSizeList: [8,12,9,5] };
    }
}
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](paging_images/paging_img4.png)
