---
title: Getting Started
page_title: Getting Started
description: This will demonstrate how to create a sample application containing a RadSlider.
slug: radslider-declaration
tags: getting,started
published: True
position: 1
---

# Getting Started

This tutorial will walk you through the creation of a sample application that contains a __RadSlider__. 

## Assembly References

In order to use the __RadSlider__ control in your projects, you have to add references to the following assemblies:

* __Telerik.Windows.Controls__
				
## Adding RadSlider to the Project

You can add __RadSlider__ in XAML or in code as demonstrated in examples 1 and 2 respectively. 

> In order to use the RadSlider control, you need to declare the following namespace: xmlns:telerik="http://schemas.telerik.com/2008/xaml/presentation"

#### __[XAML] Example 1: Adding RadSlider in XAML__
{{region xaml-radslider-declaration_0}}
	<telerik:RadSlider Value="5" Minimum="0" Maximum="100" SmallChange="1" />
{{endregion}}

#### __[C#] Example 2: Adding RadSlider in code__
{{region cs-radslider-declaration_1}}
	RadSlider slider = new RadSlider();
	slider.Maximum = 100;
	slider.Minimum = 0;
	slider.Value = 5;
	slider.SmallChange = 1;
{{endregion}}

#### __[VB.NET] Example 2: Adding RadSlider in code__
{{region vb-radslider-declaration_2}}
	Dim slider As New RadSlider()
	slider.Maximum = 100
	slider.Minimum = 0
	slider.Value = 5
	slider.SmallChange = 1
{{endregion}}

#### Figure 1: Result from Examples 1 and 2
![RadSlider](images/radslider_gettingstarted.png)

> By default the __Value__ of the RadSlider will be constantly updated while the thumb is dragged. If you want the value to be updated only once, when the thumb is released, you can set the __IsDeferredDraggingEnabled__ property to __True__.

## See Also
* [Visual Structure]({%slug radslider-visual-structure%})
* [Events]({%slug radslider-events-overview%})
* [Orientation]({%slug radslider-orientation%})
* [Ticks and tick frequency]({%slug radslider-ticks-and-tick-frequency%})