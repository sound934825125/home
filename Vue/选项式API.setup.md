## setup() 返回值

暴露给模板和其他选项式 API 钩子的对象。

	// 模板中使用 setup 返回的 count 变量
	<template><button @click="count++">{{ count }}</button></template>

	// 选项式 API 中使用 setup 返回的 count 变量
	onMounted(() => {
		console.log(count)
	})

	// 返回包含变量、方法、渲染函数的对象
	// 当返回渲染函数时将阻止其他返回值, 可通过 expose 显式声明其他返回值
	setup(){
		const count = ref(0)
		expose({ count })
		return {
			h('div', count.value)
		}
	}