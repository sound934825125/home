# VAutocomplete user

## Props

- search: String - 获取焦点时显示的文本
- `transition: false` - from makeTransitionProps

***makeFilterProps***

- customFilter: Function
- customKeyFilter: Object
- filterKeys: `title`
- filterMode: String, `default`: `intersection`
- noFilter: Boolean - 搜索时不过滤, 在服务器端过滤
- label: String - 占位符文本

***makeSelectProps***

- chips: Boolean - 选项样式
- closableChips: Boolean - 允许关闭
- eager: Boolean
- hideNoData: Boolean - 隐藏无数据时显示
- hideSelected: Boolean
- menu: Boolean
- menuIcon - `$dropdown`, 设置下拉菜单图标
- menuProps
- modelValue: `() => []`
- multiple: Boolean - 多选
- noDataText: `$vuetify.noDataText` - 设置无数据时显示的文本
- openOnClear: Boolean

***makeItemsProps***

- itemTitle - 指定 items[] 中的项作为 title
- itemValue - 指定 items[] 中的项作为 value
- itemProps - 指定 items[] 中的项作为 props
- `itemChildren: false`
- `returnObject: Boolean`

- items[] - 自动转换为包含以下键的数组
	+ title - 项的前文本
	+ value - 项的后文本
	+ props: {title, value, prependIcon, ...} - 自动转换, 传递给项 VListItem 的任何 prop
	+ raw - 原始的未被转换的 items[] 数组

## Slots

- append
- append-inner
- append-item
- prepend
- prepend-inner
- prepend-item
- clear - 删除键图标
- details
- item - 被遍历的列表选项
- label - 占位符提示文本
- loader - 加载中图标
- no-data - items 中不包含 search 内容时显示
- selection - 被选中项
- chip - 被选中项，以 chip 显示

***Item 下拉列表***

Type

	item: {
	    title: string
	    value: any
	    props: { title: string; value: any }		// 在 props itemTitle、itemValue 中指定，转换后的 item
	    children: InternalItem<unknown>[]
	    raw: unknown														// 未被转换的 item
	  }
	index: number
	props: Record<string, unknown>

Example

	<template v-slot:item="{ props, item, index }">
	  <v-list-item v-if="typeof item.raw !== 'object'" v-bind="props"></v-list-item>
	  <v-list-item
	    v-else
	    v-bind="props"
	    :prepend-avatar="item.raw.avatar"
	    :title="item.raw.name"
	    :subtitle="item.raw.group"
	  ></v-list-item>
	</template>	

***Chip 芯片显示的选中项***

	<template v-slot:chip="{ props, item }">
	  <v-chip
	    v-bind="props"
	    :prepend-avatar="item.raw.avatar"
	    :text="item.raw.name"
	  ></v-chip>
	</template>	

***NoData 无数据时显示***

	<template v-slot:no-data>
	  <v-list-item>
	    <v-list-item-title>
	      Search for your favorite
	      <strong>Cryptocurrency</strong>
	    </v-list-item-title>
	  </v-list-item>
	</template>

***Selection***

	<template v-slot:selection="{ attr, on, item, selected }">
	  <v-chip
	    v-bind="attr"
	    :input-value="selected"
	    color="blue-grey"
	    class="white--text"
	    v-on="on"
	  >
	    <v-icon start>
	      mdi-bitcoin
	    </v-icon>
	    <span v-text="item.name"></span>
	  </v-chip>
	</template>

## Events

click:append
click:appendInner
click:clear
click:prepend
click:prependInner

## VModel 双向绑定

- update:menu - Menu 打开/关闭
- update:modeValue - 被选中项 item.value 值
- update:search - 搜索文本改变

## Exposed

## SASS Variables