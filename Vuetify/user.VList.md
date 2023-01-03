# List 列表

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

## Props

- line - 指定, `one`、`two`、`three`
- single-line - 单行
- two-line - 双行
- three-line - 三行

- items - Array
	+ type - 指定项类型, `subheader`、`divider`
	+ title - 前文本, 可通过 item-title props 指定项中的值。
	+ value - 后文本, 可通过 item-value props 指定项中的值。
	+ props - Object, 等同于 v-list-item props 定制指定项
	
- density - 样式, 稠密的	
- disablesd - 禁用的
- variant - 样式
- nav - 样式, 指定为导航栏
- rounded - 样式, 指定圆角
- shaped - 样式, 指定左上、右下圆角

## VListGroup

嵌套的子列表

- value

Slots

<template v-slot:activator="{ props }">