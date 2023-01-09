# List 列表

## 组成

- VList
- VListSubheader - 列表标题
- VListItem - 列表项
- VListItemContent - 项容器, 中间内容部分
- VListItemAction - 项容器, 下方可操作部分
- VListItemActionText
- VListItemAvatar
- VListItemIcon - 项图标
- VListItemGroup - 项选择组, 多选组
- VListItemSubtitle - 项副标题
- VListItemTitle - 项标题

## VList Props

- activeColor
- activeClass
- bgColor
- disabled
- nav - 是否作为导航栏开启样式
- `lines: "one"` - 指定多行布局, `one`、`two`、`three`, 直接使用 Props 指定: `single-line`、`two-line`、`three-line`
- `itemType: type` - 指定项类型, `subheader`、`divider`

- density - 设置样式舒适/紧凑 `comfortable`、`compact`, from makeDensityProps
- `variant: 'text'` - 指定样式变体, `elevated`、`flat`、`tonal`、`outlined`、`text`、`plain`, from makeVariantProps
- color - from makeVariantProps
- rounded - 样式, 指定圆角, from makeRoundedProps
- border - from makeBorderProps
- elevation - from makeElevationProps
- `tag: div` - 指定组件以何种标签呈现, from makeTagProps
- theme - from makeThemeProps

**makeItemsProps**

- items - 通过 Props 数组指定列表项
- itemTitle - 指定 items 任意项作为 `item-title`
- itemValue - 指定 items 任意项作为 `item-value`
- itemChildren
	+ itemProps - 指定 items 任意项作为 `item-props`, 将传入 v-list-item 设置 props
- returnObject

**makeNestedProps**

- `selectStrategy: 'single-leaf'`
- `openStrategy: 'list'`
- opened
- selected
- mandatory

**makeDimensionProps 设置组件尺寸**

- height
- maxHeight
- maxWidth
- minHeight
- minWidth
- width

## VListItem Props

- active - Boolean 是否激活
- activeClass
- activeColor
- appendAvatar
- appendIcon
- prependAvatar
- prependIcon
- disabled
- lines
- link
- nav
- subtitle
- title
- value

**makeBorderProps**
**makeDensityProps**
**makeDimensionProps**
**makeElevationProps**
**makeRoundedProps**
**makeRouterProps**
**makeTagProps**
**makeThemeProps**
**makeVariantProps**

## VSlot

**VList**

- header
- item
- subheader

**VItem**

- append
- default
- prend
- subtitle
- title

## VListGroup 嵌套的子列表

	<template v-slot:activator="{ props }">

