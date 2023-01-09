## VSlot 插槽与构成

prepend 与 VAppBarNavIcon 打开的导航菜单图标

	<template v-slot:prepend>
	  <v-app-bar-nav-icon></v-app-bar-nav-icon>
	</template>	

title 与 VAppBarTitle - 标题

	<template v-slot:title>
		<v-app-bar-title>Title</v-app-bar-title>
	</template>

VSpacer - 分隔符

	<v-spacer></v-spacer>

append - 右侧放置内容和按钮组

	<template v-slot:append>
	  <v-btn icon="mdi-dots-vertical"></v-btn>
	</template>

img - 背景

	<template v-slot:image>
	  <v-img
	    gradient="to top right, rgba(19,84,122,.8), rgba(128,208,199,.8)"
	  ></v-img>
	</template>	

default

extension



## Props

## Events

update:modelValue

## SASS Variables