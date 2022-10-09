
传入通过 `_createVNode()` 创建的虚拟节点, 将它挂载到当前组件实例, 即 vm.render

	useRender(() => {
		return _createVNode(component_name<String>,props<Object>,children<Array>)
	})

获取当前组件的实例, 验证不存在则打印错误信息

	getCurrentInstance(name, message)

	getCurrentInstanceName()

	getUid()