---
layout: post
title: Bullet-Graph-Caption
description: bullet graph caption
platform: Angular
control: BulletGraph	
documentation: ug
---

# Bullet Graph Caption

**Bullet Graph** supports title and **subtitle** to convey what is represented in **Bullet Graph**. They are customized using **captionSettings** property.

## Title

**Title** is set to **Bullet Graph** using **text** property in **captionSettings**. Caption settings also include properties like location, font, and textAngle for customizing the caption of **Bullet Graph**.

{% highlight ts %}

this.quantitativeScale= {
    location: { x: 100, y: 200 },                   
    minimum: 0,
    maximum: 5,
    interval: 0.5,
    featureMeasures: [{ value: 4, comparativeMeasureValue: 3.5, category: "" }]
};
            
this.caption= {
    text: "Revenue YTD",
    textAngle: 0,
    location: {
        x: 10, y: 220
    },
    font: {
        color: 'gray',
        fontFamily: 'Segoe UI',
        fontStyle: 'bold',
        size: '14px',
        fontWeight: 'regular',
        opacity: 1
    }                        
};

{% endhighlight %}

{% highlight html %}

   <ej-bulletgraph id="bullet1" [height]=700 [width]=600 [captionSettings]="caption" 
                                       [quantitativeScaleSettings]="quantitativeScale">         
          
   </ej-bulletgraph>

{% endhighlight %}

The following screenshot displays a **Bullet Graph** with customized caption using the above code.

![](Bullet-Graph-Caption_images/Bullet-Graph-Caption_img1.png)

## Subtitle

**Subtitle** is added to **Bullet Graph** using **text** property of **subtitle** in **captionSettings**. **Subtitle** also provides properties like location, textAngle and font to customize subtitle similar to caption.

{% highlight ts %}


this.caption = {
    subTitle: {
            text: "Subtitle",
            location: { x: 20, y: 225 },
            font: {
                color: 'black',
                fontFamily: 'segoe ui',
                fontStyle: 'italic',
                size: '16px',
                fontWeight: 'regular',
                opacity: 1
            }
    } 
};

{% endhighlight %}


{% highlight html %}

<ej-bulletgraph id="bullet1" [height]=700 [width]=600 [captionSettings]="caption">         
          
</ej-bulletgraph>

{% endhighlight %}

The following screenshot displays **Bullet Graph** with a subtitle

![](Bullet-Graph-Caption_images/Bullet-Graph-Caption_img2.png)

## Indicator

You can add **Indicator** to bullet graph by enabling **visible** and setting **text** properties of **indicator** in **captionSettings**. Indicator is used to represent whether target is achieved or not with text and symbol by comparing current and target values in bullet graph. 

Indicator displays a symbol along with text which is different from caption and subtitle. Images like logos can be used in indicator instead of symbols. Indicator has properties such as **symbol**, **text**, **textSpacing**, **textAngle**, **location** and **font**.

{% highlight ts %}


this.caption = {
    indicator: {
        visible: true,
        textAngle: 0,
        location: { x: 15, y: 240 },
        text: "+ $0.5 K",
        textSpacing: 5,
        symbol: {
            color: 'green',
            shape: 'triangle',
            imageURL: "Column.png",
            size: {
                width: 10,
                height: 10
            },
            border: {
                width: 1,
                color: 'green'
            }
        },
        font: {
            color: 'green',
            fontFamily: 'Segoe UI',
            fontStyle: 'Normal ',
            size: '12px',
            fontWeight: 'regular',
            opacity: 1
        },
    }
};

{% endhighlight %}

{% highlight html %}

<ej-bulletgraph id="bullet1" [captionSettings]="caption">         
          
</ej-bulletgraph>

{% endhighlight %}

The following screenshot displays a bullet graph with indicator.

![](Bullet-Graph-Caption_images/Bullet-Graph-Caption_img3.png)

## Trim

The title, subtitle and indicator text can be overlapped to the scale group. You can avoid the overlapped text by using the enableTrim property of the captionSettings. The default value of the enableTrim is true. 

{% highlight ts %}


this.caption= {
    text: 'Bullet Graph Title',
    enableTrim : true,
};

{% endhighlight %}

{% highlight html %}

<ej-bulletgraph id="bullet1" [captionSettings]="caption">         
          
</ej-bulletgraph>

{% endhighlight %}

The following screenshot displays the BulletGraph with Trim.

![](Bullet-Graph-Caption_images/Bullet-Graph-Caption_img4.png)

## Text Placement

All the caption group elements (caption, subtitle, and indicator) in the **Bullet Graph** support text positioning by using the property **textPosition** available in all caption group elements. The properties, **textAlignment** and **textAnchor** are used to customize text placement further.

**Text Position**

The property, textPosition, is used to position the text at the top, bottom, left, and right side of the quantitative scale. The default value of this property is float. By default, text can be placed at any desired location by using the location property.

{% highlight ts %}

this.caption = {
    text: 'Bullet Graph Title',
    textPosition: 'top',
    font: {
        size: '20px',
        fontWeight: 'bold',

    }
};

{% endhighlight %}

{% highlight html %}

<ej-bulletgraph id="bullet1" [height]=150 [width]=650 [value]=8 [comparativeMeasureValue]=5 
                [captionSettings]="caption" [quantitativeScaleSettings.location.x]=120 
                [quantitativeScaleSettings.location.y]=40>         
          
</ej-bulletgraph>

{% endhighlight %}

The following screenshot displays the Bullet Graph with the title positioned above.

![](Bullet-Graph-Caption_images/Bullet-Graph-Caption_img5.png)

### Text Alignment

Alignment of text at different positions with respect to scale can be customized by using the **textAlignment** property. Text can be aligned in the **near**, **center,** and **far** locations of the scale. Text alignment depends upon **textPosition** property and is not applicable when the value of the **textPosition** property is **float**. The default value of the **textAlignment** property is **near**.

{% highlight ts %}

this.caption = {
    text: 'Revenue',
    textPosition: 'left',
    textAnchor: 'middle',
    font: {
        size: '16px',
        fontWeight: 'bold',

    },
    subTitle: {
        text: '$ in thousands',
        textPosition: 'left',
        textAlignment: 'center',
        font: {
            size: '12px',
            fontWeight: 'bold',

        }
    }
};

{% endhighlight %}

{% highlight html %}

<ej-bulletgraph id="bullet1" [height]=150 [width]=650 [value]=8 [comparativeMeasureValue]=5 
                [captionSettings]="caption" [quantitativeScaleSettings.location.x]=120 
                [quantitativeScaleSettings.location.y]=40>         
          
</ej-bulletgraph>

{% endhighlight %}

The following screenshot displays the Bullet Graph with the title and subtitle at different alignments.

![](Bullet-Graph-Caption_images/Bullet-Graph-Caption_img6.png)

### Text Anchor

Text elements aligned at the same position are anchored by using the textAnchor property. These can be anchored at the start, middle, and end. The default value of this property is start and applicable only when two or more text elements are aligned at the same position. 

{% highlight ts %}

this.caption = {
    text: 'Revenue',
    textPosition: 'left',
    textAnchor: 'middle',
    font: {
        size: '16px',
        fontWeight: 'bold',

    },
    subTitle: {
        text: '$ in thousands',
        textPosition: 'left',
        textAlignment: 'center',
        font: {
            size: '12px',
            fontWeight: 'bold',

        }
    }
};

{% endhighlight %}

{% highlight html %}

<ej-bulletgraph id="bullet1" [height]=150 [width]=650 [value]=8 [comparativeMeasureValue]=5 
                [captionSettings]="caption" [quantitativeScaleSettings.location.x]=120 
                [quantitativeScaleSettings.location.y]=40>         
          
</ej-bulletgraph>

{% endhighlight %}

![](Bullet-Graph-Caption_images/Bullet-Graph-Caption_img7.png)

### Padding

The space required between text and quantitative scale is customized by using the padding property. The default value of this property is 5 and not applicable when the value of the textPosition property is float.

{% highlight ts %}


this.caption = {
    text: 'Profit in %',
    textPosition: 'left',
    textAlignment: 'center',
    padding: 10,
    font: {
        size: '16px',
        fontWeight: 'bold',

    }
};

{% endhighlight %}

{% highlight html %}

<ej-bulletgraph id="bullet1" [height]=150 [width]=650 [value]=8 [comparativeMeasureValue]=5
                [captionSettings]="caption" [quantitativeScaleSettings.location.x]=120 
                [quantitativeScaleSettings.location.y]=40>         
          
</ej-bulletgraph>

{% endhighlight %}

![](Bullet-Graph-Caption_images/Bullet-Graph-Caption_img8.png)

## Localization

Bullet graph supports localization for its axis labels and tooltip. To render the bullet graph with specific culture you have to refer the corresponding globalize culture script and need to specify the culture name in `locale` property of bullet graph.

Enable Group Separator is used to Convert the date object to string while using the locale settings, you can set `enableGroupSeparator` property as true.



{% highlight html %}

<ej-bulletgraph id="bullet1" locale="" [enableGroupSeperator]="true">         
          
</ej-bulletgraph>

{% endhighlight %}

