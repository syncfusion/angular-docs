---
layout: post
title: Working with hyperlink customization in RichTextEditor widget
description: Working with Hyperlinks customization in RichTextEditor widget
platform: Angular
control: RichTextEditor
documentation: ug
---
# Working with Hyperlinks

A hyperlink can be insert into the editor for quick access to the related information. The hyperlink itself can be a text or an image.

## Add and Edit a hyperlink

To add a hyperlink to the editor, follow these instructions:

1. Point the cursor anywhere within the editor where you’d like to insert the link. It is also possible to select a text or an image within the editor and can be converted to the hyperlink.
2. Click the “Insert/Edit hyperlink” tool on the Toolbar.
3. In the **Web** **Address** box, type or paste the destination for the link you are creating.
4. In the **Text** box, type or edit the required text that you want to display text for the link. 

N> Leave this textbox blank if you want to display the full link as hyperlink in the editor.

5. To display additional helpful information when you place the pointer on the hyperlink, type the required text in the “Tooltip” field.
6. Click OK button to insert a hyperlink.

{% highlight html %}

<textarea id="texteditor" ej-rte [(toolsList)]="toolslist" [(tools)]="tools" [value]="val"></textarea>

{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';

@Component({
  selector: 'sd-home',
  templateUrl: 'app/components/rte/rte.component.html'
})
export class RTEComponent {
    val: string;
    toolslist: any;
    tools: Object;
    constructor() {
        this.val = "The RichTextEditor (RTE) control enables you to edit the contents with insert table and images," + " it also provides a toolbar that helps to apply rich text formats to the content entered in the TextArea.";
        this.toolslist = ["links"];
        this.tools = {
            links: ["createLink", "removeLink"]
        };
    }     
}

{% endhighlight %}

N> hyperlinks on a picture are not always visible, but the pointer’s appearance will be changed on positioning the mouse pointer over it.

## Remove a hyperlink

If you want to remove a hyperlink from a text or image, select the text or image with the hyperlink and click “Remove Hyperlink” tool from toolbar. It will keep the text or image.