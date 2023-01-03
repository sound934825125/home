# VSheet

该组件是一张纸，它是其他组件 Material Design 的基础，实现如 `border-radius`、`box-shadow`、`elevation`、`rounded`、`color` 等功能。

## Props

## SASS Variables

# VCard

卡片是 VSheet 的增强，为文本、图像、图标提供简单的界面。

## User

卡片由标题、副标题、文本、可操作区域组成。

**通过 Props 定义卡片区域**

	<v-card title="" subtitle="" text="">

**通过 VSlot 定义卡片区域**

	<v-card>
		<template v-slot:title></template>
		<template v-slot:subtitle></template>
		<template v-slot:text></template>
	</v-card>	

**通过 Components 定义卡片区域**

	<v-card>
		<v-card-item>
			<v-card-title>
			<v-card-subtitle>
		</v-card-item>	
		<v-card-text></v-card-text>
		<v-card-actions><v-btn></v-btn></v-card-actions>
	<v-card>	

## 更多组件搭配

	<v-card :loading="loading">
	<template v-slot:loader="{ isActive }">
		<v-progress :active-"isActive"></v-progress>
	</template>
	<v-img><v-card-title></v-card-title></v-img>	
		<v-card-actions>
			<v-btn @click="show = !show"></v-btn>
		</v-card-actions>
		<v-expand-transition>
			<v-card v-if="show">
				<v-divider></v-divider>
				<v-card-text></v-card-text>
			</v-card>
		</v-expand-transition>
	</v-card>

- VImg + Text - 在媒体任意位置添加文本
- VExpandTransition - VCardActions 控制过渡组件展示扩展内容
- VDivider - 在卡片中使用分割线
- VSlot Loader - 定制加载中特效

## Props

- appendAvatar - 前头像
- appendIcon- 前图标
- disabled
- flat
- hover
- image - 
- link
- prependAvatar - 后头像
- prependIcon - 后图标
- ripple
- subtitle
- text
- title

**makeThemeProps**
**makeBorderProps**
**makeDensityProps**
**makeDimensionProps**
**makeElevationProps**
**makeLoaderProps**
**makeLocationProps**
**makePositionProps**
**makeRoundedProps**
**makeRouterProps**
**makeTagProps**
**makeVariantProps**

## VCardItem Props

- appendAvatar
- appendIcon
- prependAvatar
- prependIcon
- subtitl
- title

**makeDensityProps**

## SASS Vaiables

