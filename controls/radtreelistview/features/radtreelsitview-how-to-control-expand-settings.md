---
title: IsExpandedBinding and IsExpandableBinding
page_title: IsExpandedBinding and IsExpandableBinding
description: Check our &quot;IsExpandedBinding and IsExpandableBinding&quot; documentation article for the RadTreeListView {{ site.framework_name }} control.
slug: radtreelsitview-how-to-control-expand-settings
tags: isexpandedbinding,and,isexpandablebinding
published: True
position: 2
---

# IsExpandedBinding and IsExpandableBinding

Since __Q1 2013__ release, __RadTreeListView__ has two new properties - __IsExpandedBinding__ and __IsExpandableBinding__ - which can be used to synchronize its expanded and expandable states with your view-model.

>caution Binding to the __IsExpanded__ property of __TreeListViewRow__ is not fully supported. You can consider using [IsExpandedBinding](#use-of-isexpandedbinding) property instead.

## Use of IsExpandedBinding

__IsExpandedBinding__ property can be used to show you whether a __TreeListView's__ row is expanded or not.

Follow these steps to accomplish the task:

1. For the purpose of this tutorial we will add a boolean property - __IsExpanded__ - to our __WarehouseItem__ collection:  
	>Please, note that our __WarehouseItem__ class implements the __INotifyPropertyChanged__ interface.        

#### __[C#] Example 1: Create WarehouseItem model__
{{region radtreelsitview-how-to-use-of-IsExpandedBinding_and_IsExpandableBinding_0}}

	public class WarehouseItem : INotifyPropertyChanged
	{
		public event PropertyChangedEventHandler PropertyChanged;

		private bool isExpanded;
		private string name;
		private int count;

		public WarehouseItem(string name, int count, bool isExpanded = true)
		{
			this.Name = name;
			this.IsExpanded = isExpanded;           
		}

		public string Name
		{
			get
			{
				return this.name;
			}
			set
			{
				if (value != this.name)
				{
					this.name = value;
					this.OnPropertyChanged("Name");
				}
			}
		}

		public bool IsExpanded
		{
			get
			{
				return this.isExpanded;
			}
			set
			{
				if (value != this.isExpanded)
				{
					this.isExpanded = value;
					this.OnPropertyChanged("IsExpanded");
				}
			}
		}
		protected virtual void OnPropertyChanged(PropertyChangedEventArgs args)
		{
			PropertyChangedEventHandler handler = this.PropertyChanged;
			if (handler != null)
			{
				handler(this, args);
			}
		}

		private void OnPropertyChanged(string propertyName)
		{
			this.OnPropertyChanged(new PropertyChangedEventArgs(propertyName));
		}
	}
{{endregion}}



#### __[VB.NET] Example 1: Create WarehouseItem model__
{{region radtreelsitview-how-to-use-of-IsExpandedBinding_and_IsExpandableBinding_1}}

	Public Class WarehouseItem
		Implements INotifyPropertyChanged
		Public Event PropertyChanged As PropertyChangedEventHandler

		Private m_isExpanded As Boolean
		Private m_name As String
		Private count As Integer

		Public Sub New(name As String, count As Integer, Optional isExpanded As Boolean = True)
			Me.Name = name
			Me.IsExpanded = isExpanded
		End Sub

		Public Property Name() As String
			Get
				Return Me.m_name
			End Get
			Set(value As String)
				If value <> Me.m_name Then
					Me.m_name = value
					Me.OnPropertyChanged("Name")
				End If
			End Set
		End Property

		Public Property IsExpanded() As Boolean
			Get
				Return Me.m_isExpanded
			End Get
			Set(value As Boolean)
				If value <> Me.m_isExpanded Then
					Me.m_isExpanded = value
					Me.OnPropertyChanged("IsExpanded")
				End If
			End Set
		End Property
		Protected Overridable Sub OnPropertyChanged(args As PropertyChangedEventArgs)
			Dim handler As PropertyChangedEventHandler = Me.PropertyChanged
			RaiseEvent handler(Me, args)
		End Sub

		Private Sub OnPropertyChanged(propertyName As String)
			Me.OnPropertyChanged(New PropertyChangedEventArgs(propertyName))
		End Sub
	End Class
{{endregion}}

2. Add __RadTreeListView__ as demonstrated in __Example 2__:

#### __[XAML] Example 2: Declare RadTreeListView in XAML__
{{region radtreelsitview-how-to-use-of-IsExpandedBinding_and_IsExpandableBinding_2}}
	<telerik:RadTreeListView x:Name="radTreeListView"
								 IsExpandedBinding="{Binding IsExpanded, Mode=TwoWay}"
								 AutoGenerateColumns="False">
			<telerik:RadTreeListView.ChildTableDefinitions>
				<telerik:TreeListViewTableDefinition ItemsSource="{Binding Items}" />
			</telerik:RadTreeListView.ChildTableDefinitions>
			<telerik:RadTreeListView.Columns>
				<telerik:GridViewDataColumn DataMemberBinding="{Binding Name}"
									Header="Name" />
				<telerik:GridViewDataColumn DataMemberBinding="{Binding IsExpanded}" 
									Header="Is Expanded" />
			</telerik:RadTreeListView.Columns>
		</telerik:RadTreeListView>
{{endregion}}

3. Here is a snapshot of the result:

![Rad Tree List View radtreelistview how-to-isexpanded 01png](images/RadTreeListView_radtreelistview_how-to-isexpanded_01png.PNG)

>tip A complete example of using __RadTreeListView's IsExpandedBinding__ property is available in {% if site.site_name == 'Silverlight' %}[ this online demo](https://demos.telerik.com/silverlight/#TreeListView/IsExpanded){% endif %}{% if site.site_name == 'WPF' %}[the TreeListView's IsExpanded demo](https://demos.telerik.com/wpf/){% endif %}.
          

## Use of IsExpandableBinding

The use of __IsExpandableBinding__ would be similar as shown for the __IsExpandedBinding__.

>tip A complete example of using __RadTreeListView's IsExpandedBinding__ property is available in {% if site.site_name == 'Silverlight' %}[ this online demo](https://demos.telerik.com/silverlight/#TreeListView/OnDemandDataLoading){% endif %}{% if site.site_name == 'WPF' %}[the TreeListView's OnDemandDataLoading demo](https://demos.telerik.com/wpf/){% endif %}.
          
