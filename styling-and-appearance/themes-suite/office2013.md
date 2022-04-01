---
title: Office2013 Theme
page_title: Office2013 Theme
description: This article provides an overview of the Office2013 theme from the UI for {{ site.framework_name }} suite.
slug: common-styling-appearance-office2013-theme
tags: office2013,theme,dynamic,fontsize,fontfamily
published: True
position: 3
---

<style>
.theme-palette-color {
	width:20px;
	height:20px;
	margin: auto;
	border: 1px solid black;
}

article table
{
    table-layout: auto;
}
</style>

# Office2013 Theme

The official Q3 2013 release of UI for {% if site.site_name == 'Silverlight' %}Silverlight{% endif %}{% if site.site_name == 'WPF' %}WPF{% endif %} brought a brand new __external__ theme with a flat modern UI and three color variations – `White`, `Light Gray`, `Dark Gray`.             

The following topic explains the specifics of the theme's color variations and the available font options.      

## Theme Variations

The following are the supported color variations of the Office2013 theme

* `White`&mdash;White color theme palette. This is also the default variation of the theme.
![Common Styling Appearance Office 2013 Theme 01](../images/Common_Styling_Appearance_Office2013_Theme_01.png)

* `LightGray`&mdash;Light gray theme palette.
![Common Styling Appearance Office 2013 Theme 02](../images/Common_Styling_Appearance_Office2013_Theme_02.png)

* `DarkGray`&mdash;Dark gray theme palette.
![Common Styling Appearance Office 2013 Theme 03](../images/Common_Styling_Appearance_Office2013_Theme_03.png)

This is how the `ColorVariation` enumeration looks:        

#### __[C#]__
{{region common-styling-appearance-office2013-theme_0}}
	/// <summary>
	/// Represents theme color variations.
	/// </summary>
	public enum ColorVariation
	{
		/// <summary>
		/// Represents Dark Gray Office2013 theme palette.
		/// </summary>
		DarkGray,

		/// <summary>
		/// Represents Light Gray Office2013 theme palette.
		/// </summary>
		LightGray,

		/// <summary>
		/// Represents the default White Office2013 theme palette.
		/// </summary>
		White
	}
{{endregion}}

## Theme Variation Changing

When using `NoXAML` assemblies in an application you should merge the necessary resource dictionaries from the corresponding theme assembly (in this case - `Telerik.Windows.Themes.Office2013.dll`). Alternitevely, you can merge the resource dictionaries as *.xaml files in your application (in case there is no reference to the theme assembly) in an appropriate place in your project (i.e. App.xaml). For more information about implicit styles refer to [this article]({%slug styling-apperance-implicit-styles-overview%}).        

The `Office2013 Theme` offers a very intuitive and easy way to change its color variation. You can change the variation by using the `LoadPreset` method of `Office2013Palette` in the entry point of your application. You just have to pass to the method the desired color variation as a parameter.        

For example, if you want to set the `DarkGray` color variation, you should have the following code-block in your application:
{% if site.site_name == 'WPF' %}

#### __[C#]__
{{region common-styling-appearance-office2013-theme_1}}
    public MainWindow()
    {
        Office2013Palette.LoadPreset(Office2013Palette.ColorVariation.DarkGray);

        InitializeComponent();
    }
{{endregion}}

{% endif %}
{% if site.site_name == 'Silverlight' %}

#### __[C#]__

{{region common-styling-appearance-office2013-theme_2}}
    public UserControl()
    {
        Office2013Palette.LoadPreset(Office2013Palette.ColorVariation.DarkGray);

        InitializeComponent();
    }
{{endregion}}
{% endif %}

>The `DarkGray` variation of the theme is designed with a dark background in mind and it is recommended to use such a background in your application when choosing it.

## Office2013 Palette brushes and colors
|Brush name|White| |Light Gray| |Dark Gray| |
|----------|-----|---|----------|---|---------|---|
|AccentMain|FF0072C6|<div class="theme-palette-color" style="background: #0072C6"></div>|FF0072C6|<div class="theme-palette-color" style="background: #0072C6"></div>|FF0072C6|<div class="theme-palette-color" style="background: #0072C6"></div>|
|Accent|FF0072C6|<div class="theme-palette-color" style="background: #0072C6"></div>|FF0072C6|<div class="theme-palette-color" style="background: #0072C6"></div>|FF444444|<div class="theme-palette-color" style="background: #444444"></div>|
|Main|FFFFFFFF|<div class="theme-palette-color" style="background: #FFFFFF"></div>|FFFFFFFF|<div class="theme-palette-color" style="background: #FFFFFF"></div>|FFFFFFFF|<div class="theme-palette-color" style="background: #FFFFFF"></div>|
|Inverted|FF000000|<div class="theme-palette-color" style="background: #000000"></div>|FF000000|<div class="theme-palette-color" style="background: #000000"></div>|FF000000|<div class="theme-palette-color" style="background: #000000"></div>|
|Basic|FFFDFDFD|<div class="theme-palette-color" style="background: #FDFDFD"></div>|FFFDFDFD|<div class="theme-palette-color" style="background: #"></div>|FFFDFDFD|<div class="theme-palette-color" style="background: #FDFDFD"></div>|
|Strong|FF767676|<div class="theme-palette-color" style="background: #767676"></div>|FF767676|<div class="theme-palette-color" style="background: #767676"></div>|FF767676|<div class="theme-palette-color" style="background: #767676"></div>|
|Validation|FFFF0000|<div class="theme-palette-color" style="background: #FF0000"></div>|FFFF0000|<div class="theme-palette-color" style="background: #FF0000"></div>|FFFF0000|<div class="theme-palette-color" style="background: #FF0000"></div>|
|LowLightMain|FFF1F1F1|<div class="theme-palette-color" style="background: #F1F1F1"></div>|FFF1F1F1|<div class="theme-palette-color" style="background: #F1F1F1"></div>|FFF1F1F1|<div class="theme-palette-color" style="background: #F1F1F1"></div>|
|LowLight|FFFFFFFF|<div class="theme-palette-color" style="background: #FFFFFF"></div>|FFF1F1F1|<div class="theme-palette-color" style="background: #F1F1F1"></div>|FFE5E5E5|<div class="theme-palette-color" style="background: #E5E5E5"></div>|
|LowDark|FFFFFFFF|<div class="theme-palette-color" style="background: #FFFFFF"></div>|FFFAFAFA|<div class="theme-palette-color" style="background: #FAFAFA"></div>|FFF3F3F3|<div class="theme-palette-color" style="background: #F3F3F3"></div>|
|MediumLight|FFE1E1E1|<div class="theme-palette-color" style="background: #E1E1E1"></div>|FFE1E1E1|<div class="theme-palette-color" style="background: #E1E1E1"></div>|FFE1E1E1|<div class="theme-palette-color" style="background: #E1E1E1"></div>|
|MediumDark|FFC6C6C6|<div class="theme-palette-color" style="background: #C6C6C6"></div>|FFC6C6C6|<div class="theme-palette-color" style="background: #C6C6C6"></div>|FFC6C6C6|<div class="theme-palette-color" style="background: #C6C6C6"></div>|
|HighLight|FFD4D4D4|<div class="theme-palette-color" style="background: #D4D4D4"></div>|FFC6C6C6|<div class="theme-palette-color" style="background: #C6C6C6"></div>|FFABABAB|<div class="theme-palette-color" style="background: #ABABAB"></div>|
|HighDark|FFABABAB|<div class="theme-palette-color" style="background: #ABABAB"></div>|FFABABAB|<div class="theme-palette-color" style="background: #ABABAB"></div>|FFABABAB|<div class="theme-palette-color" style="background: #ABABAB"></div>|
|EffectLow|33FFFFFF|<div class="theme-palette-color" style="background: #FFFFFF"></div>|33FFFFFF|<div class="theme-palette-color" style="background: #FFFFFF"></div>|FF0072C6|<div class="theme-palette-color" style="background: #0072C6"></div>|
|EffectHigh|33000000|<div class="theme-palette-color" style="background: #000000"></div>|33000000|<div class="theme-palette-color" style="background: #000000"></div>|800072C6|<div class="theme-palette-color" style="background: #0072C6"></div>|
|EffectAccentLow|330072C6|<div class="theme-palette-color" style="background: #0072C6"></div>|330072C6|<div class="theme-palette-color" style="background: #0072C6"></div>|330072C6|<div class="theme-palette-color" style="background: #0072C6"></div>|
|EffectAccentHigh|800072C6|<div class="theme-palette-color" style="background: #0072C6"></div>|800072C6|<div class="theme-palette-color" style="background: #0072C6"></div>|800072C6|<div class="theme-palette-color" style="background: #0072C6"></div>|

## Changing Fonts

The official Q1 2015 release of Telerik UI for {% if site.site_name == 'WPF' %}WPF{% endif %}{% if site.site_name == 'Silverlight' %}Silverlight{% endif %} introduced features that allow you to dynamically change the `FontSize` and `FontFamily` properties of all components in the application for the Office2013 theme. 

All Telerik controls use resources that are linked to one major singleton object that contains the FontSize and FontFamily properties used for the Office2013 theme. These properties are public so you can easily modify the theme resources at one single point. The most commonly used FontSize in the theme is named `FontSizeL` and its default value is __15__. The bigger font sizes are used for headers and footers while smaller ones are used inside complex controls such as `RadRibbonView`, `RadGauge`, `RadGanttView`, etc. As for the FontFamily - there is only one FontFamily resource which is named FontFamily and it is set to `Calibri`.

>Please note that for complex scenarios we strongly recommend setting font size only initially before the application is initialized. We recommend font sizes between 11px and 19px for the __FontSize__ property.

All the available __FontSizes__ and __FontFamily__ as well as their __default values__:

#### __[C#]__
{{region common-styling-appearance-office2013-theme_3}}
	Office2013Palette.Palette.FontSizeXXS = 10;
	Office2013Palette.Palette.FontSizeXS = 12; 
	Office2013Palette.Palette.FontSizeS = 13;
	Office2013Palette.Palette.FontSize = 14;
	Office2013Palette.Palette.FontSizeL = 15;
	Office2013Palette.Palette.FontSizeXL = 16;
	Office2013Palette.Palette.FontFamily = new FontFamily("Calibri");
{{endregion}}

More details regarding the usage of the rarely used font sizes inside the different controls can be found below:

* `Office2013Palette.Palette.FontSizeXXS` is used:
	* GridViewNewRow in Telerik.Windows.Controls.GridView
	
* `Office2013Palette.Palette.FontSizeXL` is used:
	* ExpressionEditor in Telerik.Windows.Controls.Expressions
	* WizzardPage in Telerik.Windows.Controls.Navigation 
	* ScheduleView's MonthView items in Telerik.Windows.Controls.ScheduleView
	
As the following example shows, you can change the default FontFamily from "Calibri" to "MonoType Corsiva" and the FontSize from __15__ to __16__ on a click of a button:

#### __[XAML]__
{{region common-styling-appearance-office2013-theme_0}}
	<StackPanel>
		<telerik:RadCalendar x:Name="Calendar" Width="250" Height="250" Margin="4 10"/>
		<telerik:RadButton HorizontalAlignment="Center" Content="Change Font" Click="OnButtonChangeFontSizeClick" />
	</StackPanel>
{{endregion}}

#### __[C#]__
{{region common-styling-appearance-office2013-theme_4}}
	private void OnButtonChangeFontSizeClick(object sender, RoutedEventArgs e)
	{
		Office2013Palette.Palette.FontSizeL = 24;
		Office2013Palette.Palette.FontSizeS = 16;
		Office2013Palette.Palette.FontFamily = new FontFamily("MonoType Corsiva");
	}
{{endregion}}

This will be the final result:

![Common Styling Appearance Office 2013 Theme 03](../images/Common_Styling_Appearance_Office2013_Theme_04.png)

## Changing Opacity 

If you need to change the opacity of the disabled elements, you can now easily do so by using the `DisabledOpacity` property of the `Office2013Palette`. Its default value is __0.3__.

#### __[C#] Changing the opacity__		
{{region cs-common-styling-appearance-office2013-theme-5}}
	Office2013Palette.Palette.DisabledOpacity = 0.5;
{{endregion}}
	
#### __[VB.NET] Changing the opacity__		
{{region vb-common-styling-appearance-office2013-theme-6}}
	Office2013Palette.Palette.DisabledOpacity = 0.5
{{endregion}}

>important When modifying fonts, colors, or other resources from the `Office2013Palette` and `StyleManager` is used as theming mechanism, the theme's `ResourceDictionary` needs to be merged in __App.xaml__ file to apply the changes.

#### __[XAML] Merging the theme's ResourceDictionary in App.xaml__
{{region styling-appearance-office2013-theme-7}}
	<Application.Resources> 
	    <ResourceDictionary> 
	        <ResourceDictionary.MergedDictionaries> 
	            <telerik:Office2013ResourceDictionary/> 
	        </ResourceDictionary.MergedDictionaries> 
	    </ResourceDictionary> 
	</Application.Resources>
{{endregion}}

## See Also
 * [Setting a Theme (Using  Implicit Styles)]({%slug styling-apperance-implicit-styles-overview%})
