---
layout: post
title: Keyboard-Interaction
description: keyboard interaction
platform: Angular
control: ColorPicker
documentation: ug
---

# Keyboard Interaction

You can use **keyboard** shortcut keys as an alternative to the mouse while using the **ColorPicker** widget. The **ColorPicker** widget allows you to perform all kinds of actions using **keyboard** shortcuts.

Keyboard shortcut keys

  <table>
    <tr>
        <th>
            Shortcut Key</th>
        <th>
            Description</th>        
    </tr>
    <tr>
        <td>
            Alt + j              
        </td>
        <td>
            Focuses into the <b>ColorPicker</b> control
        </td>
    </tr>
    <tr>
        <td>
            Enter
        </td>
        <td>
            Open / Close the Popup
        </td>
    </tr>
    <tr>
        <td>
            Up
        </td>
        <td>
            Increase the brightness value
        </td>
    </tr>
    <tr>
        <td>
            Down
        </td>
        <td>
            Decrease the brightness value
        </td>
    </tr>
    <tr>
        <td>
            Right
        </td>
        <td>
            Increase the saturation value
        </td>
    </tr>
    <tr>
        <td>
            Left
        </td>
        <td>
            Decrease the saturation value
        </td>
    </tr>
    <tr>
        <td>
            Enter
        </td>
        <td>
            Choose the current color
        </td>
    </tr>
    <tr>
        <td>
            Esc
        </td>
        <td>
            Closes the popup
        </td>
    </tr>
    <tr>
        <td>
            Tab
        </td>
        <td>
            Choose the next element
        </td>
    </tr>
    <tr>
        <td>
            Home
        </td>
        <td>
            Downwards to value 0
        </td>
    </tr>
    <tr>
        <td>
            End
        </td>
        <td>
            Upwards to value 100
        </td>
    </tr>
</table>

## Configure Keyboard Interaction

The following steps explain how you can enable **keyboard** interaction for **ColorPicker** textbox.

In the **HTML** page, add an **&lt;input&gt;** element to configure the **ColorPicker** widget and enable keyboard interaction by the **access key** property.

{% highlight html %}


    <input id="colorpicker" ej-colorpicker value="#278787" (keypress)="onkey($event)" />  

{% endhighlight %}

{% highlight javascript %}

 
    @Component({
    selector: 'ej-app',
    host: {'(window:keydown)': 'onkey($event)'},
    templateUrl: './colorpicker.component.html'
    })
    export class ColorPickerComponent { 
    onkey(event){ if(event.altKey && event.KeyCode === "74")
    $("#colorpickerWrapper").focus(); 
    }
    }

{% endhighlight %}

The following screenshot displays the output of the above code example.



![](Keyboard_Interactions_images/Keybaord_interactions_image.png) 

