
## useRender

传入通过 `_createVNode()` 创建的虚拟节点, 将它挂载到当前组件实例, 即 vm.render

	useRender(() => {
		return _createVNode(component_name<String>,props<Object>,children<Array>)
	})

## getCurrentInstance

获取当前组件的实例, 验证不存在则打印错误信息

	getCurrentInstance(name, message)

	getCurrentInstanceName()

	getUid()

## defaultComponent

根据传入值判断调用 `defineComponent` 或 `_defineComponent`

	genericComponent()

- `_defineComponent` - vue 原生 API, 通过该方法定义组件选项使其支持 TypeScript 类型推断。
-	`defineComponent(options)` - 重定义 `_defineComponent` 使支持更多类型限制

**用例**

调用 genericComponent 并传入参数 options 立即执行, 将它导出为组件 VAutocomplete

	export const VAutocomplete = genericComponent()(options)

