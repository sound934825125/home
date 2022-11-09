定义并立即执行这个匿名函数

	( function(val){alert(val)} )("打印这个值")

	( function(val){alert(val)}("打印这个值") )

	void function(val){alert(val)}("打印这个值")

	function foo(val){alert(val)}; foo("打印这个值")

将 options 传递给 genericComponent 这个函数调用, 并将这个立即执行的调用定义为 VAutocomplete

	export const VAutocomplete = genericComponent()(options)