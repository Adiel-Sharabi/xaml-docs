---
title: Getting Started
page_title: Getting Started
description: Check our &quot;Getting Started&quot; documentation article for the RadPipsPager control.
slug: radpipspager-getting-started
tags: getting started, radpipspager
published: True
position: 2
---

# Getting Started with {{ site.framework_name }} PipsPager

This tutorial will walk you through the creation of a sample application that contains a `PipsPager` control.

## Assembly References

To use RadPipsPager, add a reference to the following assembly:

* __Telerik.Windows.Controls__

## Defining the RadPipsPager

You can add RadPipsPager manually in XAML as demonstrated in the following example:

#### __[XAML] Adding RadPipsPager in XAML__
{{region radpipspager-getting-started-0}}
    <telerik:RadPipsPager/>
{{endregion}}

## Adding Items

The RadPipsPager control works with `RadPipsPagerItem` elements that are added to the `Items` collection of the control. These elements can be added both in XAML and in code.

#### __[XAML] Adding RadPipsPagerItems__
{{region radpipspager-getting-started-1}}
    <telerik:RadPipsPager>
        <telerik:RadPipsPagerItem/>
        <telerik:RadPipsPagerItem/>
        <telerik:RadPipsPagerItem/>
    </telerik:RadPipsPager>
{{endregion}}

__RadPipsPager with manually added items__

![{{ site.framework_name }} RadPipsPager with manually added items](images/radpipspager-getting-started-0.png)

## Data Binding

The RadPipsPager component allows you to navigate the items of any `ItemsControl` controls by binding to its collection.

The following example a basic scenario where the RadPipsPager is used together with another control.

#### __[C#] Creating the model__
{{region radpipspager-getting-started-2}}
    public class Person
    {
        public string Name { get; set; }
    }
{{endregion}}

#### __[VB.NET] Creating the model__
{{region radpipspager-getting-started-3}}
    Public Class Person
        Public Property Name As String
    End Class
{{endregion}}

#### __[C#] Creating the view model__
{{region radpipspager-getting-started-4}}
    public class MainViewModel
    {
        public MainViewModel()
        {
            this.People = new ObservableCollection<Person>
            {
                new Person() { Name = "Jack" },
                new Person() { Name = "Mike" },
                new Person() { Name = "Nick" }
            };
        }

        public ObservableCollection<Person> People { get; set; }
    }
{{endregion}}

#### __[VB.NET] Creating the view model__
{{region radpipspager-getting-started-5}}
    Public Class MainViewModel
        Public Sub New()
            Me.People = New ObservableCollection(Of Person) From {
                New Person() With {
                    .Name = "Jack"
                },
                New Person() With {
                    .Name = "Mike"
                },
                New Person() With {
                    .Name = "Nick"
                }
            }
        End Sub

        Public Property People As ObservableCollection(Of Person)
    End Class
{{endregion}}

#### __[XAML] Creating the view__
{{region radpipspager-getting-started-6}}
    <Grid HorizontalAlignment="Center" VerticalAlignment="Center">
        <Grid.DataContext>
            <local:MainViewModel/>
        </Grid.DataContext>
        <Grid.RowDefinitions>
            <RowDefinition Height="Auto"/>
            <RowDefinition Height="*"/>
        </Grid.RowDefinitions>
        <telerik:RadSlideView x:Name="slideView"
                              ItemsSource="{Binding People}"
                              SelectedIndex="0">
            <telerik:RadSlideView.ItemTemplate>
                <DataTemplate>
                    <TextBlock Text="{Binding Name}"
                               HorizontalAlignment="Center"/>
                </DataTemplate>
            </telerik:RadSlideView.ItemTemplate>
        </telerik:RadSlideView>
        <telerik:RadPipsPager ItemsSource="{Binding ElementName=slideView, Path=ItemsSource}"
                              SelectedItem="{Binding ElementName=slideView, Path=SelectedItem}"
                              Grid.Row="1"
                              ButtonVisibility="Visible"/>
    </Grid>
{{endregion}}

__RadPipsPager and RadSlideView result__

![{{ site.framework_name }} RadPipsPager and RadSlideView result](images/radpipspager-getting-started-1.png)

## Setting a Theme

The controls from our suite support different themes. You can see how to apply a theme different than the default one in the [Setting a Theme]({%slug styling-apperance-implicit-styles-overview%}) help article.

>important Changing the theme using implicit styles will affect all controls that have styles defined in the merged resource dictionaries. This is applicable only for the controls in the scope in which the resources are merged. 

* Choose between the themes and add reference to the corresponding theme assembly (ex: __Telerik.Windows.Themes.Windows8.dll__). You can see the different themes applied in the __Theming__ examples from our {% if site.site_name == 'WPF' %}[WPF Controls Examples](https://demos.telerik.com/wpf/){% else %}[Silverlight Controls Examples](https://demos.telerik.com/silverlight/#PanelBar/Theming){% endif %} application.

* Merge the ResourceDictionaries with the namespace required for the controls that you are using from the theme assembly. For the RadPipsPager, you will need to merge the following resources:

	* __Telerik.Windows.Controls__

The following example demonstrates how to merge the ResourceDictionaries so that they are applied globally for the entire application.

#### __[XAML] Merge the ResourceDictionaries__
{{region radpipspager-getting-started-7}}
    <Application.Resources>
    	<ResourceDictionary>
    		<ResourceDictionary.MergedDictionaries>
    			<ResourceDictionary Source="/Telerik.Windows.Themes.Windows8;component/Themes/System.Windows.xaml"/>
    			<ResourceDictionary Source="/Telerik.Windows.Themes.Windows8;component/Themes/Telerik.Windows.Controls.xaml"/>
    		</ResourceDictionary.MergedDictionaries>
    	</ResourceDictionary>
    </Application.Resources>
{{endregion}}

>Alternatively, you can use the theme of the control via the [StyleManager](https://docs.telerik.com/devtools/wpf/styling-and-appearance/stylemanager/common-styling-apperance-setting-theme-wpf).

The following image shows a RadPipsPager with the __Windows8__ theme applied.

__RadPipsPager with the Windows8 theme__

![{{ site.framework_name }} RadPipsPager with the Windows8 theme](images/radpipspager-getting-started-2.png)

## See Also
* [Navigation Buttons]({%slug radpipspager-navigation-buttons%})