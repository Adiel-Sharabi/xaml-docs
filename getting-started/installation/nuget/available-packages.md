---
title: Available NuGet Packages
page_title: Available NuGet Packages
description: "Telerik UI for WPF provides a set of NuGet packages targeting different .NET versions."
slug: nuget-available-packages
tags: available,packages,noxaml,xaml
position: 0
---

# Available NuGet Packages

Telerik UI for WPF comes with a several different packages that can be installed via the Telerik server or from a local package source.

![{{ site.framework_name }} Telerik UI for {{ site.framework_name }} Available NuGet Packages](images/nuget-available-packages-0.png)

The Telerik dlls are built against different versions of .NET starting from .NET 4 to the latest official .NET. Additionally, the dlls can be separated into two categories - [Xaml and NoXaml]({%slug xaml-vs-noxaml%}). This creates a big set of assemblies that can be downloaded which are also available as nuget packages. 

The packages can be downloaded as `.nupkg` files which can be used to [setup a local package source]({%slug nuget-package-source-setup%}) or alternatively the [online Telerik package source]({%slug nuget-package-source-setup%}) can be used. These two different options contain slightly different set of packages. This article targets to list and describe the packages.

## NuGet Local Packages

The Telerik UI for WPF product provides `.nupkg` files that can be downloaded from [your telerik.com account](https://www.telerik.com/account/product-download?product=RCWPF). The download page has the following .zip files.

### Full Packages

* `Telerik_UI_for_WPF_<version number>_NuGet_Xaml_Dev.zip`&mdash;Contains `.nupkg` files for the following __full packages__:
	* `Telerik.UI.for.Wpf.40.Xaml`
	* `Telerik.UI.for.Wpf.45.Xaml`
	* `Telerik.UI.for.Wpf.50.Xaml`
	* `Telerik.UI.for.Wpf.60.Xaml`
	* `Telerik.UI.for.Wpf.NetCore.Xaml`
	
	Each of these packages contains the all Telerik UI for WPF (Xaml) dlls for the corresponding .NET framework. __.40__ means __.NET 4__, __.45__ means __.NET 4.5__ and so on. The __.Xaml__ part at the ending of the package name indicates that it contains the [Xaml]({%slug xaml-vs-noxaml%}) version of the Telerik assemblies.
	
* `Telerik_UI_for_WPF_<version number>_NuGet_NoXaml_Dev.zip`&mdash;Contains `.nupkg` files for the following __full packages__:
	* `Telerik.UI.for.Wpf.40`
	* `Telerik.UI.for.Wpf.45`
	* `Telerik.UI.for.Wpf.50`
	* `Telerik.UI.for.Wpf.60`
	* `Telerik.UI.for.Wpf.NetCore`
	
	Each of these packages contains the all Telerik UI for WPF (NoXaml) dlls for the corresponding .NET framework. Compared to the previous set of packages, the names here don't end with __.Xaml__ which indicates that they contain the [NoXaml]({%slug xaml-vs-noxaml%}) version of the Telerik assemblies.
	
### Separate Packages

* `Telerik_UI_for_WPF_<version number>_NuGet_Separate_Packages_Xaml_Dev.zip`&mdash;This file contains __separate packages__ for each Telerik assembly.
	* `Telerik.Windows.Controls.for.Wpf.Xaml`
	* `Telerik.Windows.Controls.Navigation.for.Wpf.Xaml`
	* `Telerik.Windows.Controls.GridView.for.Wpf.Xaml`
	* `Telerik.Windows.Controls.RichTextBox.for.Wpf.Xaml`
	* etc.
	
	Each of these packages contain the corresponding Telerik ([Xaml]({%slug xaml-vs-noxaml%})) dll for all available .NET frameworks (.40, .45, .5, etc.). In case the dll is dependent on another Telerik dll, the required package will be installed automatically.
	
* `Telerik_UI_for_WPF_<version number>_NuGet_Separate_Packages_NoXaml_Dev.zip`&mdash;This file contains __separate packages__ for each Telerik assembly.
	* `Telerik.Windows.Controls.for.Wpf`
	* `Telerik.Windows.Controls.Navigation.for.Wpf`
	* `Telerik.Windows.Controls.GridView.for.Wpf`
	* `Telerik.Windows.Controls.RichTextBox.for.Wpf`
	* `Telerik.Windows.Themes.Fluent.for.Wpf`
	* `Telerik.Windows.Themes.Material.for.Wpf`
	* etc.
	
	Each of these packages contain the corresponding Telerik ([NoXaml]({%slug xaml-vs-noxaml%})) dll for all available .NET frameworks (.40, .45, .5, etc.). In case the dll is dependent on another Telerik dll, the required package will be installed automatically.	
	
## Telerik NuGet Server Packages

There is an [online package source]({%slug nuget-package-source-setup%}) that can be used to get Telerik nugets. The packages on the server are almost identical to [local](#nuget-local-package-files) ones. 

### Full Packages

The onlie package source contains full packages only for the .NET Core and later assemblies.

* `Telerik.UI.for.Wpf.NetCore`
* `Telerik.UI.for.Wpf.NetCore.Xaml`
* `Telerik.UI.for.Wpf.50`
* `Telerik.UI.for.Wpf.50.Xaml`
* `Telerik.UI.for.Wpf.60`
* `Telerik.UI.for.Wpf.60.Xaml`

These packages contain all Telerik dlls for the corresponding .NET version. The package names ending with __.Xaml__ contain the [Xaml]({%slug xaml-vs-noxaml%}) version of the Telerik dlls. The ones without .Xaml in the name have the __NoXaml__ version.

### Separate Packages

* `Telerik.Windows.Controls.for.Wpf.Xaml`
* `Telerik.Windows.Controls.for.Wpf`
* `Telerik.Windows.Controls.GridView.for.Wpf.Xaml`
* `Telerik.Windows.Controls.GridView.for.Wpf`
* `Telerik.Windows.Controls.Navigation.for.Wpf.Xaml`
* `Telerik.Windows.Controls.Navigation.for.Wpf`
* `Telerik.Windows.Themes.Fluent.for.Wpf` (theme dll)
* `Telerik.Windows.Themes.Material.for.Wpf` (theme dll)
* `Telerik.Windows.Controls.for.Wpf.fr` (localization resource)
* `Telerik.Windows.Controls.for.Wpf.de` (localization resource)
* etc.

Each of these packages contain all .NET versions of the corresponding Telerik dll. The package names ending with __.Xaml__ contain the [Xaml]({%slug xaml-vs-noxaml%}) version of the Telerik dlls. The ones without .Xaml in the name have the __NoXaml__ version.

The __oldest nuget package__ that can be found in the __Telerik NuGet Feed__ is __2016.3.1024__.
	
## NuGet Packages and Controls Localization

The Telerik controls have a built-in [localization]({%slug common-localization%}) support. To enable this, the corresponding satellite assemblies should be presented in the folder where the Telerik assemblies are installed. These assemblies are available when you install the product using the __full NuGet packages__. The __separate packages__ don't include the satellite assemblies. To support localization properly, these dlls should be installed. To do so, use also the separate packages with the language resources.

The separate package with the language resources is named `Telerik.Windows.Controls.for.Wpf.<language code>`. For example, `Telerik.Windows.Controls.for.Wpf.fr` will include the French resources. `Telerik.Windows.Controls.for.Wpf.de` will include the German resources, and so on. 

## Installing Latest Internal Build NuGet Packages

You can install and test the [Latest Internal Build]({%slug installation-installing-lib%}) (LIB) dlls provided on a weekly basis, via the NuGet Package Manager. The LIB nugets are __available only as .nupkg files__ that can be downloaded from your telerik.com account. This means that you will need to create a [local package source]({%slug nuget-package-source-setup%}) and copy the files there. You __cannot__ download LIB dlls via the online Telerik nuget server (https://nuget.telerik.com/v3/index.json](https://nuget.telerik.com/v3/index.json, because they are not available there.

When you set up the package source and place the NuGet files there, you can find them in the NuGet Package Manager. To see the LIB packages you will need also to check the __Include prerelease__ option. The LIB packages have the __-hotfix__ postfix in the version field.

![{{ site.framework_name }} Installing Latest Internal Build NuGet Packages](images/Common_InstallingFromNuGet_10_wpf.png)
