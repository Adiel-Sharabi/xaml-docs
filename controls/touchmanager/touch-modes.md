---
title: Touch Modes
page_title: Touch Modes
description: Check our &quot;Touch Modes&quot; documentation article for the TouchManager WPF control.
slug: touchmanager-touch-modes
tags: touchmode,modes,touch,manager,touchmanager
published: True
position: 4
---

# TouchManager Touch Modes

__TouchManager__ allows you to control the touch mode of the UIElement in the visual tree. You can do this using the __TouchMode__ attached property of the manager. 

>important The __IsTouchHitTestVisible__ and __ShouldLockTouch__ properties of TouchManager are __obsolete__ and __replaced__ by the __TouchMode__ property.

__TouchMode__ is an enumeration that contains the following values:
* __HitTestVisible__ (default value): The element is visible for touch input and events will route normally.
* __HitTestHidden__: The element is not visible for touch input. Touch events will be raised for the parents of the element, as if this element is not in the visual tree.
* __Locked__: The element is visible for touch input and it will capture the touch device on touch down. All touch events will be marked as handled, thus preventing event routing.
* __None__: The element will suppress all touch events. No touch events will be raised for touch input within the boundaries of the element.

#### __[XAML] Example 1: Setting TouchMode in XAML__
{{region touchmanager-touch-modes-0}}
	<Border x:Name="element" telerik:TouchManager.TouchMode="HitTestVisible" />
{{endregion}}

#### __[C#] Example 2: Setting TouchMode in code__
{{region touchmanager-touch-modes-1}}
	TouchManager.SetTouchMode(this.element, TouchMode.HitTestVisible);
{{endregion}}
	
#### __[VB.NET] Example 2: Setting TouchMode in code__
{{region touchmanager-touch-modes-2}}
	TouchManager.SetTouchMode(Me.element, TouchMode.HitTestVisible)
{{endregion}}

## TouchMode examples

This section demonstrates the TouchModes with an example containing a few nested UIElements.

__Figure 1: The logical tree of the example - parent Grid, a Border inside the grid and an Ellipse inside the border__
![TouchManager | Touch Modes Image 01](images/touchmanager_touch_modes_01.png)

__Figure 2: TouchMode.HitTestVisible__
![TouchManager | Touch Modes Image 02](images/touchmanager_touch_modes_02.png)

__Figure 3: TouchMode.HitTestHidden__
![TouchManager | Touch Modes Image 03](images/touchmanager_touch_modes_03.png)

__Figure 4: TouchMode.Locked__
![TouchManager | Touch Modes Image 04](images/touchmanager_touch_modes_04.png)

__Figure 5: TouchMode.None__
![TouchManager | Touch Modes Image 05](images/touchmanager_touch_modes_05.png)

## See Also
* [Overview]({%slug touchmanager-overview%})
* [Events]({%slug touchmanager-events%})
* [Features]({%slug touchmanager-features%})
