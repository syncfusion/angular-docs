---
layout: post
title: Customizing-the-scroll-Step
description: customizing the scroll step
platform: Angular
control: Scroller
documentation: Ug
---

# Customizing the scroll Step

The **Scroller** control allows you to specify the scroll movement step in a pixel value, this step value is added to the scrollbar position when you press the arrow key. Based on position value, the scrollbar moves in its corresponding orientation. You can achieve this by using **scrollOneStepBy.**

The following steps explains you the configuration of **scrollOneStepBy** property in **Scroller**. 

In the HTML page, add a &lt;div&gt; element to configure Scroller widget.

{% highlight html %}

    <ej-scroller id="scroll" [scrollOneStepBy]="scrollonestepby" height="300" width="600">
    <div>
        <div id="scrollerContent">
            <div>
                <div class="sampleContent">
                    <h3 style="font-size: 20px;">MVC</h3>
                    <div>
                        <p>
                            Model–view–controller (MVC) is a software architecture pattern which separates the
                            representation of information from the user's interaction with it.
                            The model consists of application data, business rules, logic, and functions. A view can be any
                            output representation of data, such as a chart or a diagram. Multiple views of the same data
                            are possible, such as a bar chart for management and a tabular view for accountants.
                            The controller mediates input, converting it to commands for the model or view.The central
                            ideas behind MVC are code reusable and in addition to dividing the application into three
                            kinds of components, the MVC design defines the interactions between them.
                        </p>
                        <ul>
                            <li>
                                <b>A controller </b>can send commands to its associated view to change the view's presentation of the model (e.g., by scrolling through a document).
                                It can also send commands to the model to update the model's state (e.g., editing a document).
                            </li>
                            <li>
                                <b>A model</b> notifies its associated views and controllers when there has been a change in its state. This notification allows the views to produce updated output, and the controllers to change the available set of commands.
                                A passive implementation of MVC omits these notifications, because the application does not require them or the software platform does not support them.
                            </li>
                            <li>
                                <b>A view</b> requests from the model the information that it needs to generate an output representation to the user.
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </div>
    </ej-scroller>
    <style type="text/css">
    #scroll{
        display:block;
    border:1px solid #bbbcbb;
    }
    .control {
        border: 1px solid #bbbcbb;
        width: 600px;
        margin: 0 auto;
        height: 300px;
    }

    .sampleContent {
        width: 700px;
        padding: 15px;
    }
    </style>

{% endhighlight %}

{% highlight html %}
	
import { Component } from '@angular/core';
@Component({
  selector: 'ej-app',
  templateUrl: './default.component.html'
})
export class DefaultComponent {
    scrollonestepby: number;
    constructor() {
        this.scrollonestepby = 50;
       
    }
}

{% endhighlight %}

The following screenshot displays the **Scroller** control with scroll step value.

![](/Angular/Scroller/Customizing-the-scroll-Step_images/Customizing-the-scroll-Step_img1.png)

