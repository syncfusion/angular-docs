---
title: Field-List
description: field list
platform: Angular
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, js pivotgrid
---

# PivotTable Field List

## Initialization  
Field List, also known as Pivot Schema Designer, allows user to add, rearrange, filter and remove fields to show data in PivotGrid exactly the way they want.

Based on the datasource, OLAP, bound to the PivotGrid control, PivotTable Field List will be automatically populated with Cube Information or Field Names. PivotTable Field List provides an Excel like appearance and behavior.

In-order to initialize PivotTable Field List, first you need to define a “div” tag with an appropriate “id” attribute which acts as a container for the widget. Then you need to initialize the PivotTable Field List by using the **“EJ.PivotSchemaDesigner”** method.

{% highlight html %}

<!--Create a tag which acts as a container for PivotGrid-->
 <ej-pivotgrid id="PivotGrid1" [enableGroupingBar]="true" pivotTableFieldListID="PivotSchemaDesigner1" >
</ej-pivotgrid>
<!--Create a tag which acts as a container for PivotTable Field List-->
<ej-pivotschemadesigner id="PivotSchemaDesigner1"></ej-pivotschemadesigner>

{% endhighlight %}
 
![](PivotTable-Field-List_images/olapclientfieldlsit.png)

## Layout
The top portion of the layout shows Field or Cube items in a categorized way. They can be dynamically added into the report either by drag and drop option or through simple check box selection.
 
On item(s) selection they will be placed in Row section by default except numeric based item(s) or measures, which will alone be placed in the Value section by default.
 
The bottom portion of the layout is segregated as below.

* Report Filter: Exclusively designed to filter an item(s) placed in this particular position of the layout. 
* Value Section: The value label usually displays the numeric value item(s) present in the report.
* Column Section: It is used to display item(s) as column header and values in the PivotGrid control. 
* Row Section: It is used to display item(s) as row header and values in the PivotGrid control.

## UI Interactions

### By Drag and Drop

You can alter the report on fly through drag-and-drop operation. You can drag any item from Field List and drop into column, row, value or filter section available at the bottom of the Field List.

![](PivotTable-Field-List_images/ui-operartion.png)
 
### By Treeview Selection
 
You can also alter the report on fly through check and uncheck option as an alternate. By default, fields will be added to the Row Label when checked.

![](PivotTable-Field-List_images/pivotfield.png)
 
### By Context Menu
 
You can also alter the report by using context menu.

![](PivotTable-Field-List_images/Olap_Pivotbutton_Context.png)

![](PivotTable-Field-List_images/Olap_Treeview_Context.png)

## Searching Values
Search option available in Field List allows you to search a specific value that needs to be filtered from the list of values inside the filter pop-up window.

![](PivotTable-Field-List_images/filterclick.png)

![](PivotTable-Field-List_images/search.png)

## Filtering
Values can be filtered by checking/unchecking the check box besides them, inside the filter pop-up window. At least one value needed to be checked state while filtering otherwise “Ok” button will be disabled.

![](PivotTable-Field-List_images/filterclick.png)

![](PivotTable-Field-List_images/filter.png)
