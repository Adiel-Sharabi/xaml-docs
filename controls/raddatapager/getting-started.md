---
title: Getting Started
page_title: Getting Started
description: Check our "Getting Started" documentation article for the RadDataPager WPF control.
slug: raddatapager-getting-started
tags: getting,started
published: True
position: 3
---

# Getting Started

The __RadDataPager__ is a control that allows you to split your data into pages and display it in a user-friendly way. This topic will help you quickly get started using the control.

>To learn more about the concepts behind the __RadDataPager__ you can read the [Paging Essentials]({%slug raddapager-features-paging-essentials%}) topic first.

## Adding RadDataPager

In order to use __RadDataPager__ in your project, you need to add references to the following assemblies:

* __Telerik.Windows.Controls.dll__

* __Telerik.Windows.Controls.Data.dll__

* __Telerik.Windows.Data.dll__

After adding references to the aforementioned dlls, you can declare a new __RadDataPager__ as any normal __Silverlight/WPF__ control.

>To use the __RadDataPager__ in the XAML you have to add the following namespace declaration: __xmlns:telerik="http://schemas.telerik.com/2008/xaml/presentation"__ 

#### __[XAML] Example 1: Declare a RadDataPager__

{{region raddatapager-getting-started_0}}

	<telerik:RadDataPager x:Name="radDataPager" />
{{endregion}}

## Configuring the RadDataPager

__RadDataPager__ allows to be configured via the properties it exposes. You can do the following:

* Manage the size of the pages via the __PageSize__ property. [Read more]({%slug raddatapager-features-page-size%})

* Show and hide visual elements of a pager via the __DisplayMode__ property. [Read more]({%slug raddatapager-features-display-modes%})

* Implement infinite paging. [Read more]({%slug raddatapager-features-infinite-paging%})

## Paging a Collection

>To learn more about the use of the __Source__ and the __PagedSource__ properties, please read [this topic]({%slug raddatapager-features-source-and-paged-source%}).
         
>tip __RadDataPager__ internally uses a __QueryableCollectionView__ for its paging mechanism, which relies on the __Skip__ method. This requires the __OrderBy__ method to be called over the source collection, so that it is sorted.

__RadDataPager__ can page any collection that implements the __IEnumerable__ interface. The only thing that you have to do is to pass the collection to its __Source__ property.

The collection in this example will hold business objects of type Club. You can prepare a simple collection of clubs and pass it to the __Source__ property of the __RadDataPager__.

Create your __RadDataPager__ and make some basic configurations to it.

#### __[XAML] Example 2: RadDataPager bound to a collection__

{{region raddatapager-getting-started_2}}
	<telerik:RadDataPager x:Name="radDataPager"
	                      PageSize="5" 
	                      Source="{Binding Clubs}"/>
{{endregion}}

After the collection is passed to the __Source__ property, it will get split into pages. In order to learn how to access the paged collection, please read the next section.

## Exposing the Paged Collection

>tip Instead of using the __PagedSource__ property you can also wrap your collection in an __IPagedCollectionView__ before passing it to the __Source__ property. To learn more read [this topic]({%slug raddatapager-features-source-and-paged-source%}).

The paged collection inside the __RadDataPager__ can be accessed via the __PagedSource__ property. It exposes the set of data belonging to the current page. Here is an example of a __ListBox__ that displays the data paged by the __RadDataPager__.

#### __[XAML] Example 3: ListBox exposing the paged collection__

{{region raddatapager-getting-started_3}}

	<Grid x:Name="LayoutRoot"
	        Background="White">
	    <Grid.RowDefinitions>
	        <RowDefinition />
	        <RowDefinition Height="Auto" />
	    </Grid.RowDefinitions>
	      <ListBox Name="itemsControl"
	               ItemsSource="{Binding PagedSource, ElementName=radDataPager}"/>
	    <telerik:RadDataPager x:Name="radDataPager"
	                            Grid.Row="1"
	                            DisplayMode="All"
	                            PageSize="5"                          
	                            Margin="0,10,0,0" 
	                            Source="{Binding Clubs}"/>
	</Grid>
{{endregion}}

#### __Figure 1: Paged ListBox__
![Paged ListBox](images/RadDataPager_GettingStarted_02.PNG)

## Paging RadGridView

Using the **PagedSource** property, you can also apply paging to a RadGridView control. You only need to set this source as the **ItemsSource** collection of the control.

The collection in **Example 4** holds business objects of type __Employee__. You need to pass this collection to the **Source** property of the **RadDataPager**. After that, bind the ItemsSource property to the PagedSource collection using __ElementName__ binding.

#### __[XAML] Example 4: Paging RadGridView__

{{region raddatapager-getting-started_4}}

	<Grid x:Name="LayoutRoot"
	        Background="White">    
	    <Grid.RowDefinitions>
	        <RowDefinition />
	        <RowDefinition Height="Auto" />
	    </Grid.RowDefinitions>
	    <telerik:RadGridView x:Name="radGridView"
	                         ItemsSource="{Binding PagedSource, ElementName=radDataPager}"
	                         AutoGenerateColumns="False">
	        <telerik:RadGridView.Columns>
	            <telerik:GridViewDataColumn DataMemberBinding="{Binding Name}" />
	            <telerik:GridViewDataColumn DataMemberBinding="{Binding CompanyName}" />
	            <telerik:GridViewDataColumn DataMemberBinding="{Binding Title}" />
	        </telerik:RadGridView.Columns>
	    </telerik:RadGridView>
	    <telerik:RadDataPager x:Name="radDataPager"
	                          Source="{Binding Employees}"
	                          PageSize="5" />
	</Grid>
{{endregion}}

#### __Figure 2: Paged RadGridView__
![Paged RadGridView](images/RadDataPager_GettingStarted_01.png)

## See Also

* [Paging Essentials]({%slug raddapager-features-paging-essentials%})
* [Visual Structure]({%slug raddatapager-visual-structure%})
* [Events]({%slug raddatapager-events-overview%})
* [Source and Paged Source]({%slug raddatapager-features-source-and-paged-source%})
