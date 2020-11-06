---
title: SpellCheck - Responsive
description: How to set the spellcheck, responsive to screen resolutions
platform: Angular
control: spellcheck
documentation: ug
keywords: Responsive, Responsive spellcheck dialog, Resize spellcheck dialog
---
# Responsive

The SpellCheck control has support for responsive behavior based on client browser’s width and height. To enable responsive, `isResponsive` property should be true.

The following code example describes the above behavior.

{% highlight html %}

<ej-spellcheck id="SpellCheck" contenteditable="true" style="display:block" [dictionarySettings]="dictionary" [contextMenuSettings.enable]="false" [isResponsive]="true"]>
    Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes. The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
</ej-spellcheck>

{% endhighlight %}

The dialog of SpellCheck control is rendering based on the client browser’s width and height. Refer to the following code to render the SpellCheck dialog control with responsive.

{% highlight html %}

<ej-spellcheck id="SpellCheck" contenteditable="true" style="display:block" [dictionarySettings]="dictionary" [contextMenuSettings.enable]="false" [isResponsive]="true">
    Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes. The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
</ej-spellcheck>
<input id="CheckSpell" type="button" class="ejinputtext" style="height:30px" value="Spell check" (click)="checkErrors($event)" />

{% endhighlight %}

{% highlight javascript %}

export class SpellCheckComponent {
    public dictionary: any;
    constructor() {
        this.dictionary = {
            dictionaryUrl: "http://js.syncfusion.com/ejServices/api/SpellCheck/CheckWords",
            customDictionaryUrl: "http://js.syncfusion.com/ejServices/api/SpellCheck/AddToDictionary"
        };
    }
    checkErrors() {
        let spellObj = $('#SpellCheck').data('ejSpellCheck');
        spellObj.showDialog();
    }    
}
{% endhighlight %}

Mobile Rendering Screenshot:

![](Responsive_Images/Responsive_Image.png)