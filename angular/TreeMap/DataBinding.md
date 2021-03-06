---
layout: post
title: DataBinding
description: databinding
platform: Angular
control: TreeMap
documentation: ug
---

# DataBinding

**TreeMap** control supports Data Binding and it can be achieved using `dataSource` property.

The `dataSource` property accepts the collection values as input. For example, you can provide the list of objects as input. The following code illustrates you on how to bind a flat collection as datasource for **TreeMap**.

{% highlight ts%}
import { Component, ViewEncapsulation} from '@angular/core';
import { DataService} from '../service/data.service';

@Component({
selector:"ej-app",
templateUrl:"src/treemap/treemap.component.html",
providers:[DataService]
})
export class TreemapComponent{
dataSource: any;
  constructor(dataService:DataService) {
    this.population_data=dataService.treemapData();
  }
}
{% endhighlight %}

{% highlight ts %}
export class DataService{
// DataService file containing treemap data in treemapData method
    treemapData():Array<any>{
        return[
                   { Continent: "Asia", Region: "Southern Asia", Growth: 1.32, Population: 1749046000 },
                   { Continent: "Asia", Region: "Eastern Asia", Growth: 0.57, Population: 1620807000 },
                   { Continent: "Asia", Region: "South-Eastern Asia", Growth: 1.20, Population: 618793000 },
                   { Continent: "Asia", Region: "Western Asia", Growth: 1.98, Population: 245707000 },
                   { Continent: "Asia", Region: "Central Asia", Growth: 1.43, Population: 64370000 },
                   { Continent: "Europe", Region: "Europe", Growth: 0.10, Population: 742452000 },
                   { Continent: "America", Region: "South America", Growth: 1.06, Population: 406740000 },
                   { Continent: "America", Region: "Northern America", Growth: 0.85, Population: 355361000 },
                   { Continent: "America", Region: "Central America", Growth: 1.40, Population: 167387000 },
                   { Continent: "Africa", Region: "Eastern Africa", Growth: 2.89, Population: 373202000 },
                   { Continent: "Africa", Region: "Western Africa", Growth: 2.78, Population: 331255000 },
                   { Continent: "Africa", Region: "Northern Africa", Growth: 1.70, Population: 210002000 },
                   { Continent: "Africa", Region: "Middle Africa", Growth: 2.79, Population: 135750000 },
                   { Continent: "Africa", Region: "Southern Africa", Growth: 0.91, Population: 60425000 }
        ];
    }


{% endhighlight %}

{% highlight html %}

<ej-treemap id="treemap"  [dataSource]="population_data" colorValuePath= "Growth"
                                                   weightValuePath= "Population">
               
</ej-treemap>

{% endhighlight %}

