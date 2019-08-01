---
title: Customize Expander Animation
page_title: Customize Expander Animation
description: This article shows how to disable or enable and also customize the RadExpander default expand/collapse animations.
slug: radexpander-howto-animation
tags: expander,animation
published: True
position: 1
---

# Expander Animation

The RadExpander control has an animation enabled by default. 

To disable or enable the animation, set the __AnimationManager.IsAnimationEnabled__ attached property on RadExpander. 

#### __[XAML] Example 1: Disabling animation in XAML__
{{region radexpander-howto-animation_0}}
	<telerik:RadExpander telerik:AnimationManager.IsAnimationEnabled="False" />
{{endregion}}

#### __[C#] Example 2: Disabling animation in code__
{{region radexpander-howto-animation_1}}        
	AnimationManager.SetIsAnimationEnabled(this.radExpander, false);
{{endregion}}

#### __[VB.NET] Example 2: Disabling animation in code__
{{region radexpander-howto-animation_2}}    
	AnimationManager.SetIsAnimationEnabled(Me.radExpander, False)            
{{endregion}}

## Customize Animations

To customize RadExpander animations, use the __AnimationManager.AnimationSelector__ property. The supported animation class is ExpanderExpandCollapseAnimation which exposes few properties to customize the animation.

#### __[XAML] Example 3: Change the speed of the animations using the SpeedRatio property (when ExpandDirection is Up or Down)__
{{region radexpander-howto-animation_3}}
	<telerik:RadExpander>
		<telerik:RadExpander.Content >
			<Grid>
				<Grid.RowDefinitions>
					<RowDefinition Height="20"/>
					<RowDefinition Height="20"/>
					<RowDefinition Height="20"/>
				</Grid.RowDefinitions>
				<TextBox Grid.Row="0">My content</TextBox>
				<TextBox Grid.Row="1">My content</TextBox>
				<TextBox Grid.Row="2">My content</TextBox>
			</Grid>
		</telerik:RadExpander.Content>
		<telerik:AnimationManager.AnimationSelector>
			<telerik:AnimationSelector>
				<telerik:ExpanderExpandCollapseAnimation AnimationName="Expand" 
														 Direction="In"
														 SpeedRatio="0.2"
														 TargetElementName="Content" />
				<telerik:ExpanderExpandCollapseAnimation AnimationName="Collapse" 
														 Direction="Out"
														 SpeedRatio="0.2"
														 TargetElementName="Content" />
			</telerik:AnimationSelector>
		</telerik:AnimationManager.AnimationSelector>
	</telerik:RadExpander>
{{endregion}}

> The previous code snippet is applicable only when the __ExpandDirection__ property of __RadExpander__ is set to Up or Down. The default value is __Down__.

When the __ExpandDirection__ property is set to Right or Left you need to use different __AnimationNames__ for the __ExpanderExpandCollapseAnimation__ objects. The expand AnimationName is "ExpandHorizontal" and the collapse AnimationName is "CollapseHorizontal".

#### __[XAML] Example 4: Change the speed of the animations using the SpeedRatio property (when ExpandDirection is Right or Left)__
{{region radexpander-howto-animation_4}}
	<telerik:RadExpander ExpandDirection="Left">
		<telerik:RadExpander.Content >
				<Grid>
					<Grid.RowDefinitions>
						<RowDefinition Height="20"/>
						<RowDefinition Height="20"/>
						<RowDefinition Height="20"/>
					</Grid.RowDefinitions>
					<TextBox Grid.Row="0">My content</TextBox>
					<TextBox Grid.Row="1">My content</TextBox>
					<TextBox Grid.Row="2">My content</TextBox>
				</Grid>
		</telerik:RadExpander.Content>
		<telerik:AnimationManager.AnimationSelector>
			<telerik:AnimationSelector>
				<telerik:ExpanderExpandCollapseAnimation AnimationName="ExpandHorizontal" 
														 Direction="In"
														 SpeedRatio="0.2"
														 TargetElementName="Content" />
				<telerik:ExpanderExpandCollapseAnimation AnimationName="CollapseHorizontal" 
														 Direction="Out"
														 SpeedRatio="0.2"
														 TargetElementName="Content" />
			</telerik:AnimationSelector>
		</telerik:AnimationManager.AnimationSelector>
	</telerik:RadExpander>
{{endregion}}

## See Also
* [Getting Started]({%slug expander-getting-started%})
* [Expand Direction]({%slug radexpander-features-expand_direction%})
