---
title: Theme Palettes
page_title: Theme Palettes
description: How to access and modify the Telerik theme palettes in WPF.
slug: styling-apperance-theme-palettes
tags: switching,custom,styles,with,themes,at,runtime,palettes,dynamic,change,update
published: True
position: 5
---

# Theme Palettes

Most Telerik themes support palette helper objects that contain the main resources of the theme (colors, font sizes, etc.). This allows easier access and modification of commonly used resources, thus customizing the applied theme. 

The examples in this article show the `Windows11Palette`, but the same approach is applicable for all palettes. See what themes support palettes in the [Available Themes]({%slug common-styling-appearance-available-themes%}) article. The name of the palette class is created by combining the theme name + *Palette* at the end. Examples: `MaterialPalette`, `FluentPalette`, `Office2019Palette`.

## Changing Palette Settings in Code

The palette object can be accessed and modified in code-behind by using the corresponding properties of the palette class (ex: `Windows11Palette`). The settings should happen before the UI is initialized. For example, in the `OnStartup` override of the `App` class or just before the `InitializeComponent` call of the main window.

#### __[C#] Setting palette colors in code__
{{region styling-apperance-theme-palettes-0}}
	public partial class App : Application
    {
        protected override void OnStartup(StartupEventArgs e)
        {
            Windows11Palette.Palette.AccentColor = (Color)ColorConverter.ConvertFromString("#27C106");
            Windows11Palette.Palette.CornerRadius = new CornerRadius(5);
            Windows11Palette.Palette.DisabledOpacity = 0.3;
            Windows11Palette.Palette.FontSize = 24;
            Windows11Palette.Palette.ValidationColor = Colors.Red;
            // etc.
            
            base.OnStartup(e);
        }
    }
{{endregion}}

## Changing Palette Settings in XAML
 
The palette resources can be replaced also in XAML. This can be done by re-defining the resource in XAML and using the same x:Key as the original resource used by the palette. __This approach is applicable with .NET 4.5 and later.__

To define or modify a theme brush or another theme resource in XAML, use the corresponding markup extension class (ex: `Windows11ResourceKey`).

#### __[XAML] Replacing a default palette resource in the App.xaml file globally for all Telerik controls that use this resource__
{{region styling-apperance-theme-palettes-1}}
	<Application.Resources>
		<SolidColorBrush x:Key="{x:Static telerik:Windows11ResourceKey.AccentBrush}" Color="Purple" />
	</Application.Resources>
{{endregion}}

#### __[XAML] Replacing a default palette resource for a single control instance__
{{region styling-apperance-theme-palettes-2}}
	<telerik:RadButton>
		<telerik:RadButton.Resources>
			<!-- Control-specific modification -->
			<SolidColorBrush x:Key="{x:Static telerik:Windows11ResourceKey.AccentBrush}" Color="Purple" />
		</telerik:RadButton.Resources>
	</telerik:RadButton>
{{endregion}}

## Theme Color Variations

Some of the Telerik themes provide predefined sets of colors (color variations). Applying a color variation goes through the palette color settings and apply the predefined values. See what themes support color variations in the [Available Themes]({%slug common-styling-appearance-available-themes%}) article. 

To apply a color variation, call the `LoadPreset` method of the corresponding palette clas (ex: `Windows11Palette`). The variations are acessed through the `ColorVariation` enum of the palette.

#### __[C#] Setting color variation__
{{region styling-apperance-theme-palettes-3}}
	public partial class App : Application
    {
        protected override void OnStartup(StartupEventArgs e)
        {
            Windows11Palette.LoadPreset(Windows11Palette.ColorVariation.Dark);
            base.OnStartup(e);
        }
    }
{{endregion}}	

## Using Palette Resources Stand-Alone

The palette resources can be accessed in XAML and used to style any WPF control using the corresponding markup extension class (ex: `Windows11Resource`). 

#### __[XAML] Using the Windows11Resource markup extension__
{{region styling-apperance-theme-palettes-4}}
	<TextBlock Text="A text block colored with the Windows11 AccentBrush" 
			   Foreground="{telerik:Windows11Resource ResourceKey=AccentBrush}" />
{{endregion}}

## See Also  
* [Setting a Theme]({%slug styling-apperance-implicit-styles-overview%})
* [Color Theme Generator]({%slug common-styling-color-theme-generator%})
* [Windows11 Theme]({%slug common-styling-appearance-windows11-theme%})
* [Office2019 Theme]({%slug common-styling-appearance-Office2019-theme%})
* [Fluent Theme]({%slug common-styling-appearance-fluent-theme%})