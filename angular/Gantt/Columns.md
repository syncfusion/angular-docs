---
layout: post
title: Columns
description: columns
platform: Angular
control: Gantt
documentation: ug
api: /api/js/ejgantt
---
# Columns

The column displays the information from a bounded data source and it will be editable to update the task details through TreeGrid.

## Column edit types

Gantt supports the following types of column editors,

  * String 
  * Date
  * Datetime
  * Numeric
  * Maskedit
  * Currency
  * Dropdown
  
## Format column

It is possible to format a column using ‘load’ event. The following code examples show how to format the ‘progress’ column with percentage value.

{% highlight javascript %}

<ej-gantt id="GanttControl" (load)="onGanttLoad($event)">
</ej-gantt>

{% endhighlight %}

{% highlight javascript %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
    templateUrl: 'app/app.component.html',
})
export class AppComponent {
    public scheduleHeaderSettings: any;
  constructor() {
     //...
  }
   onGanttLoad(sender) {
        var gantt = $("#GanttControl").ejGantt("instance");
        var columns = gantt.getColumns();
        columns[5]["format"] = "{0:p0}";
    }
}

{% endhighlight %}

Note: For more numeric format strings, please refer this [link](https://msdn.microsoft.com/library/dwhawy9k(v=vs.100).aspx).

For more date format strings, please refer this [link](https://msdn.microsoft.com/library/az4se3k1(v=vs.100).aspx).

## Column Resizing

You can change the width of the column to show the entire text of the column by resizing the column. The following code example shows you how to enable the Column Resize feature at **Gantt** initialize.

{% highlight javascript %}

<ej-gantt id="GanttControl" [allowColumnResize]="true">
</ej-gantt>

{% endhighlight %}

## Column Template

Column template is used to customize the column’s look and feel, based on requirement. 

The following code example shows you how to display a column with resource images.

place the following JsRender template in index.html file.

{% highlight javascript %}

<script type="text/x-jsrender" id="columnTemplate">

    {{"{{"}}if #data['resourceNames']{{}}}}

    <div style="display:inline-block;position:relative;left:10px;top:1px">

        <img src="images/gantt/{{'{{'}}:#data['resourceNames']{{}}}}.png" height="40px" />

    </div>

    <div style='display:inline-block;width:100%;position:relative;left:10px;top:2px'>{{:#data['resourceNames']{{}}}}</div>

    {{"{{"}}/if{{}}}}

</script>

{% endhighlight %}

{% highlight javascript %}

<ej-gantt id="GanttControl"  
        scheduleEndDate= "03/01/2014"
        resourceInfoMapping= "resourceId"
        resourceNameMapping= "resourceName"
        resourceIdMapping= "resourceId"
        [resources]= "columnTemplateResource"
        [allowGanttChartEditing]= "false" 
        (load)="onGanttLoad($event)">
</ej-gantt>

{% endhighlight %}

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html',
})
export class AppComponent {
    public columnTemplateResource: any;
    public ganttData: any;
    constructor() {
        this.columnTemplateResource = [{ resourceId: 1, resourceName: "Project Manager" },
            { resourceId: 2, resourceName: "Software Analyst" },
            { resourceId: 3, resourceName: "Developer" },
            { resourceId: 4, resourceName: "Testing Engineer" }
        ];
        this.ganttData = [{
            taskID: 1,
            taskName: "Project Schedule",
            startDate: "02/03/2014",
            endDate: "03/07/2014",
            subtasks: [{
                taskID: 2,
                taskName: "Planning",
                startDate: "02/03/2014",
                endDate: "02/07/2014",
                subtasks: [{
                        taskID: 3,
                        taskName: "Plan timeline",
                        startDate: "02/03/2014",
                        endDate: "02/07/2014",
                        duration: 6,
                        progress: "60",
                        resourceId: [1]
                    },
                    //...
                ]
            }, ]
        }];
    }
    onGanttLoad(sender) {
        var gantt = $("#gantt").ejGantt("instance");
        var columns = gantt.getColumns();
        columns[2].visible = columns[3].visible = false;
        columns[4].isTemplateColumn = true;
        columns[4].templateID = "columnTemplate";
        columns[4].width = "172";
    }
}

{% endhighlight %}

The following screenshot displays the customized column in Gantt control.

![](Columns_images/Columns_img7.png)

## Column menu

### Show column chooser

Gantt supports enabling and disabling the visibility of the columns dynamically with the [showColumnChooser](/api/js/ejgantt#members:showcolumnchooser "showColumnChooser") property. The visibility of the custom columns can also be toggled with this property. Column chooser option is rendered as a sub menu item within the column menu in the Gantt columns. 

![](Columns_images/Columns_img2.png)

The column menu is enabled with the [showColumnChooser](/api/js/ejgantt#members:showcolumnchooser "showColumnChooser") property, where the default value for this property is `false`.

The column menu provides the following options:

* Sort Ascending
* Sort Descending
* Columns 

Sort Ascending and Sort Descending options can be enabled or disabled with the [allowSorting](/api/js/ejgantt#members:allowsorting "allowSorting") property. Single level sorting can be performed with these options. To perform multilevel sorting, [allowMultiSorting](/api/js/ejgantt#members:allowmultisorting "allowMultiSorting") property should be enabled. You can also disable the visibility of a particular column in the column collection manually by setting the `visible` property to `false`.

{% highlight javascript %}

<ej-gantt id="GanttControl"
    [showColumnChooser]= "true"
    [allowSorting]="true"
    [allowMultiSorting]= "true"
    [allowColumnResize]="true">
</ej-gantt>

{% endhighlight %}

The following screenshot displays the column chooser in the Gantt control.

![](Columns_images/Columns_img3.png)

### Show column options

You can customize the column with some more options with the [showColumnOptions](/api/js/ejgantt#members:showcolumnoptions "showColumnOptions") property. Insert new column, delete column and update the header text of the column can be done with this property.

![](Columns_images/Columns_img4.png)

The column options can be enable or disabled with showColumnOptions property, where the default value for this property is false.

The column options provide the following options:

* Insert column left
* Insert column right
* Delete column
* Rename column

Inserting column provides the dialog to enter the details for the column

![](Columns_images/Columns_img5.png)

These fields can be customized with [columnDialogFields](/api/js/ejgantt#members:columndialogfields "columnDialogFields") this property. The following shows you how to customize these fields.

{% highlight javascript %}

<ej-gantt id="GanttControl"
    [showColumnChooser]= "true"
    [showColumnOptions]="true"
    [columnDialogFields]="columnDialogFields">
</ej-gantt>

{% endhighlight %}

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html',
})
export class AppComponent {
    public columnDialogFields: any;
    constructor() {
        this.columnDialogFields = ["field", "headerText", "editType"]
    }
}

{% endhighlight %}

![](Columns_images/Columns_img6.png)

