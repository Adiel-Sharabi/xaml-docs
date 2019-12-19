---
title: Creating an Application and Adding Telerik Controls
page_title: Creating an Application and Adding Telerik Controls
description: Creating an Application and Adding Telerik Controls
slug: installation-adding-to-application-create-application-and-adding-control
tags: creating,an,application,and,adding,ui,for
published: True
position: 1
---

# Creating an Application and Adding Telerik Controls

The following topic describes what steps you should perform in order to add the Telerik UI for {{ site.site_name }} in your application. There are two ways to do this - first one is to install Telerik Extensions for VisualStudio. The second one is by adding the necessary assemblies as references in your application manually. No matter which of the two manners you will choose, you will be able to use the Toolbox to create your application.

## Creating Application with Telerik Visual Studio Extensions

1. Open [Microsoft Visual Studio]{% if site.site_name == 'Silverlight' %}({%slug installation-system-requirements%}){% endif %}{% if site.site_name == 'WPF' %}({%slug installation-system-requirements-wpf%}){% endif %}.

2. Create new Telerik {{ site.site_name }} application. {% if site.site_name == 'WPF' %}For more information, check out the [Create Project]({%slug radcontrols-for-wpf-vs-extensions-project-creation%}) article.{% endif %}
	
	#### __Figure 1: Creating new Telerik application__	
	{% if site.site_name == 'Silverlight' %}
	![Creating new Telerik application](images/installation-adding-to-application-create-application-and-adding-control-0.png)
	{% else %}
	![Creating new Telerik application](images/installation-adding-to-application-create-application-and-adding-control-1.png)

	>You can choose __.Net Framework 4.0__ or __.Net Framework 4.5__ for your application.
	{% endif %}

3. Choose the application template. The options are a blank template or one of the MS Office inspired application templates. Choose the Blank option.
	
	#### __Figure 2: Choosing an application template__
	![Choosing an application template](images/installation-adding-to-application-create-application-and-adding-control-2.png)

	At this point the project references only the common Telerik.Windows.Controls.dll. 

4. {% if site.site_name == 'WPF' %}[Configure the project]({%slug radcontrols-for-wpf-vs-extensions-project-configuration%}){% endif %}{% if site.site_name == 'Silverlight' %}[Configure the project]({%slug radcontrols-for-silverlight-vs-extensions-project-configuration%}){% endif %} using the Project Configuration Wizard. This will add the dlls required by the controls you want to use. When you open the wizard you can select the  control you are going to use from the list (or search them in the search box). Clicking OK will add all required references for the controls.

	#### __Figure 3: Adding references to the charting controls__
	![Common Installing Creating Application 013 WPF](images/installation-adding-to-application-create-application-and-adding-control-3.png)	

	> This step is optional and you will need it only if use controls that are not defined in Telerik.Windows.Controls.dll.

## Creating Application and Manually Referencing the Telerik Assemblies

1. Open [Microsoft Visual Studio]{% if site.site_name == 'Silverlight' %}({%slug installation-system-requirements%}){% else %}({%slug installation-system-requirements-wpf%}){% endif %}.
          	
2. Create a new {{ site.site_name }} application.
	
	#### __Figure 4: Creating new {{ site.site_name }} application__
	![Creating new application](images/installation-adding-to-application-create-application-and-adding-control-4.png)

3. Add references to the Telerik assemblies. There are two options to do this.
	
	* [Drag a Telerik control from the toolbox](#dragging-controls-from-visual-studio-toolbox). When the control gets dropped onto the Visual Studio designer's surface, Visual Studio will automatically add the corresponding references.
	
	* Manually reference the Telerik dlls from the UI for {{ site.site_name }} installation folder.	The binaries are located in the *UI for {{ site.site_name }} installation folder/Binaries/ or *UI for {{ site.site_name }} installation folder/Binaries.NoXaml/*. To learn about the differences between the dlls in the **Binaries** and the **Binaries.NoXaml** folders, check out the [Xaml vs NoXaml]({%slug xaml-vs-noxaml%}) article.
	
## Dragging Controls from Visual Studio Toolbox

* Add the Telerik {{ site.site_name }} controls to the {% if site.framework_name == 'WPF' %}[Visual Studio Toolbox]({%slug installation-adding-to-vs-2015-toolbox-wpf%}){% else %}[Visual Studio Toolbox]({%slug installation-adding-to-vs-2015-toolbox-sl%}){% endif %}.

	>tip See the assemblies required by each Telerik control in the {% if site.site_name == 'Silverlight' %}[Controls Dependencies]({%slug installation-installing-controls-dependencies%}){% else %}[Controls Dependencies]({%slug installation-installing-controls-dependencies-wpf%}){% endif %} article.

* Open {% if site.site_name == 'WPF' %}MainWindow.xaml{% else %}MainPage.xaml{% endif %} of the project you have previously created (in the [Creating Application and Manually Referencing the Telerik Assemblies](#creating-application-and-manually-referencing-the-telerik-assemblies) section).

* Select any Telerik control in the Visual Studio Toolbox.

* Drag and drop the control in the Visual Studio XAML designer. 

	{% if site.site_name == 'WPF' %}
	#### __[XAML] Example 1: RadButton XAML automatically generated by dropping the control onto the Visual Studio designer__
	{{region installation-adding-to-application-create-application-and-adding-control-0}}
		<Window x:Class="WpfApplication1.Window1"
			xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
			xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
			xmlns:telerik="http://schemas.telerik.com/2008/xaml/presentation"
			Title="Window1" Height="300" Width="300">
			<Grid>
				<telerik:RadButton></telerik:RadButton>
			</Grid>
		</Window>
	{{endregion}}
	{% else %}
	#### __[XAML] Example 1: RadButton XAML automatically generated by dropping the control onto the Visual Studio designer__
	{{region installation-adding-to-application-create-application-and-adding-control-1}}
		<UserControl 
			x:Class="Test.MainPage"
			xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" 
			xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
			xmlns:d="http://schemas.microsoft.com/expression/blend/2008" 
			xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
			xmlns:telerik="http://schemas.telerik.com/2008/xaml/presentation"    
			mc:Ignorable="d" d:DesignWidth="640" d:DesignHeight="480">
		  <Grid x:Name="LayoutRoot">
				<telerik:RadTreeView></telerik:RadTreeView>
		  </Grid>
		</UserControl>
	{{endregion}}
	{% endif %}

> After dropping a control, Visual Studio automatically creates a namespace that points to the appropriate assembly. If you want to manually set up a namespace take a look at the [Namespace Declaration]({%slug installation-adding-application-namespace-declaration%}) topic.

## See Also  
 * [Namespace Declaration]({%slug installation-adding-application-namespace-declaration%})
 * [Xaml vs NoXaml]({%slug xaml-vs-noxaml%})
 * [Using IntelliSense in Visual Studio]({%slug installation-adding-application-using-intellisense-vs%})
 {% if site.site_name == 'WPF' %}
 * [Upgrading Telerik UI Trial to Telerik UI Developer License or Newer Version]({%slug installation-upgrading-from-trial-to-developer-license-wpf%}) 
 {% else %}
 * [Upgrading Telerik UI Trial to Telerik UI Developer License or Newer Version]({%slug installation-upgrading-from-trial-to-developer-license%}) 
 {% endif %}
