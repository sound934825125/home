# VAutocomplete

## 调用

- makeSelectProps
- makeFilterProps
- useFilter
- makeTransitionProps
- forwardRefs
- useItems
- useLocale
- useProxiedModel

**components**

- VCheckboxBtn
- VChip
- VDefaultsProvider
- VList
- VListItem
- VMenu
- VTextField

**util**

- genericComponent
- useRender
- wrapInArray

## 组件结构

> |- VAutocomplete > VtextField > input
> |
> | |- VMenu > VList 											遮罩, 弹出可选项
> | | |- VListItem slot:no-data 					无数据时显示
> | | |- VListItem 												遍历显示可选项
> | | | |- slot:prepend -> VCheckboxBtn
> | | | |- slot:title
> | 
> | |- div 																遍历显示选中项
> | | |- VDefaultsProvider 								hasChips 则显示默认样式 
> | | |- template 												否则通过插槽显示
> | | | |- slot:selection -> slot:chip
> | | | |- span 													分隔符

## 方法与函数

	highlightResult(text, matches, length)

	select(item)

**监听器**

	watch(isFocused, val => {})

	watch(search, val => {})

## 事件处理函数

- onClear(e)
- onClickControl()
- onKeydown(e)
- onInput(e)
- onAfterLeave()