---
title: Hide The Application Menu
page_title: Hide The Application Menu
description: Hide The Application Menu
slug: radribbonview-how-to-hide-the-application-menu
tags: hide,the,application,menu
published: True
position: 1
include_in_navigation: False
---

# Hide The Application Menu

Whenever you want to prevent the end-user from using the application menu, you should set the RadRibbonView's __ApplicationButtonVisibility__ property to __Visibility.Collapsed__. For more information about the Application Menu different functionalities, take a look at the [Application Menu]({%slug radribbonview-applicationmenu%}) topic.		

#### __[XAML] Example 1: Hiding Application Menu__
{{region xaml-radbuttons-features-toggle-switch-button_0}}
	<telerik:RadRibbonView ApplicationButtonVisibility="Collapsed"/>
{{endregion}}

## See Also
 * [Handle double click on application button]({%slug radribbonview-how-to-handle-double-click-on-application-button%})
 * [Add Screen Tips in the Code Behind]({%slug radribbonview-howto-add-screentips-code-behind%})