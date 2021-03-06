---
layout: post
title: Timescale-Modes
description: timescale modes
platform: Angular
control: Gantt
documentation: ug
api: /api/js/ejgantt
---

# Timescale customization

Gantt contains built-in support to switch over various schedule modes. You can achieve this by defining a schedule header type for the Gantt.

## Schedule Header Types

Gantt contains the following built-in schedule header types

* Hour – Minute
* Day – Hour
* Week – Day
* Month – Week
* Year – Month

The following code example illustrates you on how to change the schedule mode.

### Week schedule mode

In the Week schedule mode, the upper part of the schedule header displays the weeks, whereas the bottom half of the header displays the days. Refer the following code example.

{% highlight javascript %}

<ej-gantt id="GanttControl" [scheduleHeaderSettings]="scheduleHeaderSettings"
    //...>
</ej-gantt>

{% endhighlight %}

{% highlight javascript %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
    templateUrl: 'app/app.component.html'
})
export class AppComponent {
  public scheduleHeaderSettings:any;
  constructor() {
   //...
   this.scheduleHeaderSettings={
        scheduleHeaderType: ej.Gantt.ScheduleHeaderType.Week,
        weekHeaderFormat: "MMM dd , yyyy",
        dayHeaderFormat: "ddd",
    } 
  }
}

{% endhighlight %}

The following screenshot illustrates the Week Schedule in Gantt control.

![](Timescale-Modes_images/Timescale-Modes_img1.png)

### Month schedule mode

In the Week schedule mode, the upper part of the schedule header displays the Months whereas the bottom header of the schedule displays its corresponding Weeks. Refer the following code example.

{% highlight javascript %}

<ej-gantt id="GanttControl" [scheduleHeaderSettings]="scheduleHeaderSettings"
    //...>
</ej-gantt>

{% endhighlight %}

{% highlight javascript %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
    templateUrl: 'app/app.component.html'
})
export class AppComponent {
   public scheduleHeaderSettings:any;
   constructor() {
   //...
   this.scheduleHeaderSettings={
        scheduleHeaderType: ej.Gantt.ScheduleHeaderType.Month,
        monthHeaderFormat: "MMM yyyy",
        weekHeaderFormat: "M/dd",
    }
  }
}

{% endhighlight %}

The following screenshot illustrates the Month Schedule in Gantt control.

![](Timescale-Modes_images/Timescale-Modes_img2.png)

### Year schedule mode

In the Week schedule mode, the upper schedule header displays the Years, whereas the bottom header displays its corresponding Months. Refer the following code example.

{% highlight javascript %}

<ej-gantt id="GanttControl" [scheduleHeaderSettings]="scheduleHeaderSettings"
    //...>
</ej-gantt>

{% endhighlight %}

{% highlight javascript %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
    templateUrl: 'app/app.component.html'
})
export class AppComponent {
   public scheduleHeaderSettings:any;
   constructor() {
   //...
   this.scheduleHeaderSettings={
        scheduleHeaderType: ej.Gantt.ScheduleHeaderType.Year,
        yearHeaderFormat: "yyyy",
        monthHeaderFormat: "MMM",
    }
  }
}

{% endhighlight %}

The following screen shot shows the Year Schedule in Gantt control.

![](Timescale-Modes_images/Timescale-Modes_img3.png)

### Day schedule mode

In the Week schedule mode, the upper part of the header displays the Days, whereas the bottom schedule header displays its corresponding Hours. Refer the following code example.

{% highlight javascript %}

<ej-gantt id="GanttControl" [scheduleHeaderSettings]="scheduleHeaderSettings"
    //...>
</ej-gantt>

{% endhighlight %}

{% highlight javascript %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
    templateUrl: 'app/app.component.html'
})
export class AppComponent {
   public scheduleHeaderSettings:any;
   constructor() {
   //...
   this.scheduleHeaderSettings={
        scheduleHeaderType: ej.Gantt.ScheduleHeaderType.Day,
        dayHeaderFormat: " dd,MM,yy ",
        hourHeaderFormat: "HH",
    }
  }
}

{% endhighlight %}

The following screenshot illustrates the Day Schedule in Gantt control.

![](Timescale-Modes_images/Timescale-Modes_img4.png)

### Hour schedule mode

An Hour-Minute Schedule Mode tracks the tasks in minutes scale. In this mode, upper schedule header displays hour scale and the lower schedule header displays its corresponding Minutes. The minute split-up in the lower schedule header can be defined by using the [minutesPerInterval](/api/js/ejgantt#members:scheduleheadersettings-minutesperinterval) enumeration property. The enumeration values of the [minutesPerInterval](/api/js/ejgantt#members:scheduleheadersettings-minutesperinterval) are,

* Auto 
* oneMinute
* fiveMinutes
* fifteenMinutes
* thirtyMinutes

The value `auto`, automatically calculates the interval depending upon the `scheduleStartDate` and `scheduleEndDate`, whereas the other enumeration values splits up accordingly.

The Hour Schedule Mode supports both the `minute` and `hour` duration units.

{% highlight javascript %}

<ej-gantt id="GanttControl" dateFormat="M/d/yyyy hh:mm:ss tt" 
    [scheduleHeaderSettings]="scheduleHeaderSettings"
    [durationUnit]="durationUnit"
    //...>
</ej-gantt>

{% endhighlight %}

{% highlight javascript %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
    templateUrl: 'app/app.component.html'
})
export class AppComponent {
    public scheduleHeaderSettings:any;
    public durationUnit;
    constructor() {
    //...
    this.durationUnit=ej.Gantt.DurationUnit.Minute
    this.scheduleHeaderSettings={
        scheduleHeaderType: ej.Gantt.ScheduleHeaderType.Hour,
        minutesPerInterval: ej.Gantt.minutesPerInterval.FiveMinutes,
    }
  }
}

{% endhighlight %}

![](Timescale-Modes_images/Timescale-Modes_img5.png)

## Week start day customization

In Gantt, we can customize week start day by using `weekStartDay` property.
By default the weekStartDay will be assigned with 0 which specifies the start day of the week.

In week schedule mode, week starts with Sunday by default. But we can customize the week start day by using below code example

{% highlight javascript %}

<ej-gantt id="GanttControl" [scheduleHeaderSettings]="scheduleHeaderSettings"
    //...>
</ej-gantt>

{% endhighlight %}

{% highlight javascript %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
    templateUrl: 'app/app.component.html'
})
export class AppComponent {
   public scheduleHeaderSettings:any;
   constructor() {
   //...
   this.scheduleHeaderSettings={
        scheduleHeaderType: ej.Gantt.ScheduleHeaderType.Week,
		weekStartDay : 3        
    }
  }
}

{% endhighlight %}


## Rounding off timescale (schedule) start date

You can able to round off the schedule start date in a project by using the [timescaleStartDateMode](/api/js/ejgantt#members:scheduleheadersettings-timescalestartdatemode) property. It is possible to set the following values to the property,

* auto
* month
* week
* year

The value `auto`, automatically calculates the schedule header depending on the datasource values, whereas the other enumeration values rounds off the schedule header accordingly. For Instance, in year schedule if you set [timescaleStartDateMode](/api/js/ejgantt#members:scheduleheadersettings-timescalestartdatemode) as `month` then the schedule header will start from the immediate month of the schedule instead of starting from beginning of the year.

{% highlight javascript %}

<ej-gantt id="GanttControl" [scheduleHeaderSettings]="scheduleHeaderSettings"
    //...>
</ej-gantt>

{% endhighlight %}

{% highlight javascript %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
    templateUrl: 'app/app.component.html'
})
export class AppComponent {
   public scheduleHeaderSettings:any;
   constructor() {
   //...
   this.scheduleHeaderSettings={
        scheduleHeaderType: ej.Gantt.ScheduleHeaderType.Year,
        timescaleStartDateMode: ej.Gantt.TimescaleRoundMode.Month,
    }
  }
}

{% endhighlight %}

![](Timescale-Modes_images/Timescale-Modes_img6.png)

[Click](http://js.syncfusion.com/demos/web/#!/bootstrap/gantt/schedulingconcepts/timescalemodes) here to view the timescale modes in Gantt.

## Customize automatic timescale update action

In Gantt, schedule timeline was automatically updated when the tasks date values are updated beyond the schedule date values. This can be enabled/disabled by using [`updateTimescaleView`](/api/angular/ejgantt#members:scheduleheadersettings-updatetimescaleview "scheduleHeaderSettings.updateTimescaleView") property.
The following code snippets shows how to prevent the automatic timescale update in Gantt.

{% highlight javascript %}
	<ej-gantt id="GanttControl" [scheduleHeaderSettings]="scheduleHeaderSettings"
		//...>
	</ej-gantt>
{% endhighlight %}

{% highlight javascript %}
	import { Component } from '@angular/core';
	@Component({
	selector: 'ej-app',
    templateUrl: 'app/app.component.html'
	})
	export class AppComponent {
		public scheduleHeaderSettings:any;
		constructor() {
		//...
		this.scheduleHeaderSettings={
			scheduleHeaderType: ej.Gantt.ScheduleHeaderType.Week,
			updateTimescaleView : false        
    }
  }
}
{% endhighlight %}

The following screenshot illustrates the behavior of `updateTimescaleView` property.

![](Timescale-Modes_images/Timescale-Modes_img7.png)
At Initial load
{:.caption}

![](Timescale-Modes_images/Timescale-Modes_img8.png)
`updateTimescaleView` property as `false`
{:.caption}

![](Timescale-Modes_images/Timescale-Modes_img9.png)
`updateTimescaleView` property as `true`
{:.caption}