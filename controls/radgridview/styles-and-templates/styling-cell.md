---
title: Styling Cells
page_title: Styling Cells
description: Get started with Telerik's {{ site.framework_name }} DataGrid and learn how to create an appropriate style targeting the Cell element.
slug: gridview-styling-cell
tags: styling,cells
published: True
position: 4
---

# Styling Cells

>tipBefore reading this topic, you might find it useful to get familiar with the [Template Structure of the GridViewCell]({%slug radgridview-styles-and-templates-templates-structure%}#gridviewcell).

#### __Figure 1: GridViewCell template structure__

![Telerik {{ site.framework_name }} DataGrid Cell Template](images/gridviewcell-template.png)

> The examples from this article assume that the RadGridView is set up as demonstrated in its [Getting Started]({%slug gridview-getting-started2%}) article.

## Targeting the GridViewCell Element

In order to style all __RadGridView__ cells of an application, you should create an appropriate style targeting the __GridViewCell__ element.

You have two options:

* To create an empty style and set it up on your own.

* To copy the default style of the control and modify it.

>To learn how to modify the default GridViewCell style, please refer to the [Modifying Default Styles]({%slug gridview-modifying-default-styles%}) article.

#### __[XAML] Example 1: Styling all cells of an application__

{{region xaml-gridview-styling-cell_0}}
	<Application.Resources>
        <ResourceDictionary>
            <Style TargetType="telerik:GridViewCell">
                <Setter Property="VerticalContentAlignment" Value="Top"/>
                <Setter Property="HorizontalContentAlignment" Value="Center"/>
                <Setter Property="Background" Value="#ffcc00"/>
            </Style>
        </ResourceDictionary>
    </Application.Resources>
{{endregion}}

>If you're using [Implicit Styles]({%slug styling-apperance-implicit-styles-overview%}), you should base your style on the __GridViewCellStyle__.

#### __Figure 2: RadGridView with styled cells in the Office2016 theme__

![Telerik {{ site.framework_name }} DataGrid-Cell-Styled](images/RadGridView-Cell-Styled.png)

## Setting a Column's CellStyle

__RadGridView Cells__ can also be styled by creating an appropriate __Style__ for the **GridViewCell** element and setting it as the __CellStyle__ property of the respective __GridView Column__. 

#### __[XAML] Example 2: Setting a column's CellStyle__
{{region xaml-gridview-styling-cell_1}}
	<Grid>
        <Grid.Resources>
            <Style x:Key="GridViewCellStyle" TargetType="telerik:GridViewCell">
                <Setter Property="VerticalContentAlignment" Value="Top"/>
                <Setter Property="HorizontalContentAlignment" Value="Center"/>
                <Setter Property="Background" Value="#ffcc00"/>
            </Style>
        </Grid.Resources>

        <telerik:RadGridView ItemsSource="{Binding Clubs}"
                             AutoGenerateColumns="False"
                             GroupRenderMode="Flat">
            <telerik:RadGridView.Columns>
                <telerik:GridViewDataColumn DataMemberBinding="{Binding Name}"
	                Header="Name"
	                CellStyle="{StaticResource GridViewCellStyle}" />
            </telerik:RadGridView.Columns>
        </telerik:RadGridView>
    </Grid>
{{endregion}}

## Setting a Column's CellStyleSelector

You could also use a column's **CellStyleSelector** property to style cells differently based on a specific condition. More details about how this can be achieved can be found in the [CellStyleSelector article]({%slug gridview-cell-style-selector%}).

## Setting the SelectedBackground of the Cell

As of __R3 2018 RadGridView__ supports setting the Background of the selected cell, by setting the **SelectedBackground** property of the GridViewCell.

#### __[XAML] Example 3: Setting the SelectedBackground of the GridViewCell__
{{region xaml-gridview-styling-cell_2}}
	<Application.Resources>
        <ResourceDictionary>
            <Style TargetType="telerik:GridViewCell">
                <Setter Property="SelectedBackground" Value="Bisque" />
            </Style>
        </ResourceDictionary>
    </Application.Resources>
{{endregion}}

#### __Figure 3: Result from Example 3 in the Office2016 theme__
![Telerik {{ site.framework_name }} DataGrid-selected-background-cell](images/gridview-selectedbackground-cell.png)

## Setting the BorderBrush of the CurrentCell

As of __R3 2018 RadGridView__ supports setting the BorderBrush of the current cell, by setting the **CurrentBorderBrush** property of the GridViewCell. 

**Example 4** demonstrates how you can set the borderbrush of the current cell to transparent. You can compare **Figure 3** and **Figure 4** to notice that the border of the current cell is not visible.

#### __[XAML] Example 4: Setting the CurrentBorderBrush of the GridViewCell__
{{region xaml-gridview-styling-cell_3}}
	<Application.Resources>
        <ResourceDictionary>
            <Style TargetType="telerik:GridViewCell">
                <Setter Property="CurrentBorderBrush" Value="Transparent" />
            </Style>
        </ResourceDictionary>
    </Application.Resources>
{{endregion}}

#### __Figure 4: Result from Example 4 in the Office2016 theme__
![Telerik {{ site.framework_name }} DataGrid-currentborderbrush](images/gridview-currentborderbrush.png)

> After you have set the __CurrentBorderBrush__ to __Transparent__, if you start navigating through the cells with the keyboard, you will be able to see the FocusVisual border. If you want to hide it as well, you can set the __FocusVisualStyle__ of the GridViewCell to null through a style similar to __Example 4__.

## Setting the MouseOverBackground of the Cell

As of __R1 2019 SP1__ RadGridView supports changing the MouseOver Background of its cells, through the __MouseOverBackground__ property of the GridViewCell. This is demonstrated in __Example 5__.

#### __[XAML] Example 5: Setting the MouseOverBackground of the GridViewCell__
{{region xaml-gridview-styling-cell_4}}
	<Application.Resources>
        <ResourceDictionary>
            <Style TargetType="telerik:GridViewCell" >
                <Setter Property="MouseOverBackground" Value="Pink" />
            </Style>
        </ResourceDictionary>
    </Application.Resources>
{{endregion}}

#### __Figure 5: Result from Example 5 in the Office2016 theme__
![RadGridView with MouseOverBackground for the cells](images/gridviewcell-mouseoverbackground.png)

> In order for the MouseOverBackground of the cell to take effect, the [SelectionUnit]({%slug gridview-selection-basics%}#selection-units) of RadGridView should be __Mixed__ or __Cell__.

## See Also

 * [Styling the GridViewEditorPresenter]({%slug gridview-styling-editorpresenter%})

 * [Styling the Column Footers]({%slug gridview-styling-column-footers%})

 * [Styling the Column Headers]({%slug gridview-styling-column-headers%})

 * [Change Background for Disabled Grid Elements]({%slug gridview-how-to-set-background-disabled-cell%})
