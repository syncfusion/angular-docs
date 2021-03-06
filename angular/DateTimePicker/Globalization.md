---
layout: post
title: Localization
description: localization
platform: Angular
control: DateTimePicker
documentation: ug
---

# Globalization

DateTimePicker has been provided with built-in localization support, so that it can adapt based on culture specific locale defined for it. 

More than 350 culture specific files are available to localize the datetime.

N> Seven culture-specific script files are available in the below specified location. For all other culture files, please download from the [GitHub](https://github.com/syncfusion/ej-global/tree/master/i18n) location.

If you want to change month names to your culture month just replace month names with your culture month names or your customized format.

The following code example is used to set DateTimePicker in Spanish language.

{% highlight javascript %}

    calendars: {
       standard: {
          firstDay: 1,
          days: {
             names: ["domingo", "lunes", "martes", "miércoles", "jueves", "viernes", "sábado"],
             namesAbbr: ["do.", "lu.", "ma.", "mi.", "ju.", "vi.", "sá."],
             namesShort: ["D", "L", "M", "X", "J", "V", "S"]
          },
          months: {
             names: ["enero", "febrero", "marzo", "abril", "mayo", "junio", "julio", "agosto", "septiembre", "octubre", "noviembre", "diciembre", ""],
             namesAbbr: ["ene.", "feb.", "mar.", "abr.", "may.", "jun.", "jul.", "ago.", "sep.", "oct.", "nov.", "dic.", ""]
          },
          AM: null,
          PM: null,
          eras: [{
             "name": "d. C.",
             "start": null,
             "offset": 0
          }],
          patterns: {
             d: "dd/MM/yyyy",
             D: "dddd, d' de 'MMMM' de 'yyyy",
             t: "H:mm",
             T: "H:mm:ss",
             f: "dddd, d' de 'MMMM' de 'yyyy H:mm",
             F: "dddd, d' de 'MMMM' de 'yyyy H:mm:ss",
             M: "d' de 'MMMM",
             Y: "MMMM' de 'yyyy"
          }
       }
    }

{% endhighlight %}

The following code example can be used to get Spanish culture in **DateTimePicker**.

Add the following code in your **HTML** page.


{% highlight html %}
  
<div align="center">
<input type="text" id="dateTime" ej-datetimepicker width='200' [locale]="locale" [buttonText]="button" [(ngModel)]="value">
</div>                     

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: './default.component.html'
})
export class DefaultComponent {
    value: any;
    locale: string;
    button: Object;
    constructor() {
        this.value = Date();
        this.locale = "es-ES";
        this.button = { today: "hoy", timeNow: "ahora", done: "hecho", timeTitle: "tiempo" };
    }
}

{% endhighlight %}

![](/DateTimePicker/Globalization_images/Globalization_img1.png)

