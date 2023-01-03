# source.VAutocomplete

## 组件结构

> |- VAutocomplete > VtextField > input
> |
> | |- VMenu > VList 								遮罩, 弹出可选项
> | | |- noData 									无数据时显示: 存在 slots.noData 则使用, 否则使用 props.noDataText 文本创建 VListItem
> | | |- VListItem 									遍历显示选项: 存在 slots.item 则使用, 否则创建 VListItem
> | | | |- 如果 props.multiple 使用 prepend 插槽创建 VCheckboxBtn
> | | | |- 使用 title 插槽显示 search 值
> | 
> | |- div 											遍历显示选中项
> | | |- VDefaultsProvider 							hasChips 则显示默认样式 
> | | |- template 									否则通过插槽显示
> | | | |- slot:selection -> slot:chip
> | | | |- span 									分隔符

## 自定义事件 `onClick:control` `onClick:input`

VAutocomplete > VTextField

处理函数 onControlClick



VTextField
    function onControlClick(e) {
      onFocus();
      emit('click:control', e);
    }



VInput > VField > input > "onClick": e => emit('click:input', e),


