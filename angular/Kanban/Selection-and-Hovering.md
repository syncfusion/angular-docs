---
layout: post
title: Selection and Hovering
description: Selection and Hovering
documentation: ug
platform: Angular
keywords: selection, hovering,kanban selection, hovering
---

# Selection and Hovering

Selection provides an interactive support to highlight the card that you select. Selection can be done through simple Mouse down or Keyboard interaction. To enable selection, set [`allowSelection`](https://help.syncfusion.com/api/js/ejkanban#members:allowselection) as true.

You can see the mouse hovering effect on the corresponding cards using [`allowHover`](https://help.syncfusion.com/api/js/ejkanban#members:allowhover) property. By default selection and hovering is `true`.

## Types of Selection

Two types of selections available in Kanban are,

1.	Single
2.	Multiple

### Single Selection

To enable single selection by setting [`selectionType`](https://help.syncfusion.com/api/js/ejkanban#members:selectiontype) property as single.

### Multiple Selection

Multiple selections is an interactive support to select a group of cards in Kanban by mouse or keyboard interactions. To enable multiple selections by set [`selectionType`](https://help.syncfusion.com/api/js/ejkanban#members:selectiontype) property as `multiple`.

You can select multiple random cards below key press.

<table>
<tr>
<th>
Keys</th><th>
Description</th></tr>
<tr>
<td>
Ctrl + mouse left</td><td>
To select multiple random cards.</td></tr>
<tr>
<td>
Shift + mouse left </td><td>
To continuous cards select.</td></tr>
</table>

To unselect selected cards, by press “Shift + mouse left” click on selected row.

The following code example describes the above behavior.

{% highlight html %}

<ej-kanban [dataSource]="kanbanData" keyField="Status" fields.primaryKey="Id" fields.content="Summary" fields.tag="Tags" [query]="query" selectionType="multiple">
    <e-kanban-columns>
        <e-kanban-column key="Open" headerText="Backlog"></e-kanban-column>
        <e-kanban-column key="InProgress" headerText="In Progress"></e-kanban-column>
        <e-kanban-column key="Close" headerText="Done"></e-kanban-column>
    </e-kanban-columns>
</ej-kanban>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
import { NorthwindService } from '../../services/northwind.service';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/components/kanban/default.component.html',
  providers: [NorthwindService]
})
export class DefaultComponent {
  public kanbanData: any;
    constructor(private northwindService: NorthwindService) {
        this.kanbanData = northwindService.getTasks();
        this.query = ej.Query().from('kanbanData').take(30);       
    }
}

{% endhighlight %}


The following output is displayed as a result of the above code example.

![](Selection_images/selection_img1.png)