# VTextField

## Props

- autofocus: Boolean - 
- counter: [Boolean, Number, String] - 
- counterValue: Function - 
- hint: String - 
- persistentHint: Boolean - 
- prefix: String - 
- placeholder: String - 
- persistentPlaceholder: Boolean - 
- persistentCounter: Boolean - 
- suffix: String - 
- type: { type: String, default: 'text' },

**makeVInputProps**

- id
- appendIcon: IconValue - 
- prependIcon: IconValue - 
- hideDetails: [Boolean, String] - 
- messages: {type: [Array， String], default: () => []} - 
- 'onClick:prepend': EventProp - 
- 'onClick:append': EventProp - 
- direction
***
	direction: {
    type: String,
    default: 'horizontal', 
    validator: v => ['horizontal', 'vertical'].includes(v)
	} 
***

***makeDensityProps***
***makeValidationProps***

**makeVFieldProps**

- appendInnerIcon: IconValue - 
- bgColor: String - 
- clearable: Boolean - 
- clearIcon: { type: IconValue, default: '$clear' } - 
- active: Boolean - 
- color: String - 
- dirty: Boolean - 
- disabled: Boolean - 
- error: Boolean - 
- label: String - 
- persistentClear: Boolean - 
- prependInnerIcon: IconValue - 
- reverse: Boolean - 
- singleLine: Boolean - 
- 'onClick:clear': EventProp - 
- 'onClick:appendInner': EventProp - 
- 'onClick:prependInner': EventProp - 
- variant
***
	variant: {
	type: String,
	default: 'filled',
	validator: v => allowedVariants.includes(v)
	}
***

***makeThemeProps***
***makeLoaderProps***

## 组件结构

***

	|- VTextField > VInput
	||- slot default
	|||- VField > input
	||||- span props.prefix 前缀
	||||- slots.default 和 inputNode 存在插槽内容
	||||- cloneVNode(inputNode) 不存在插槽内容
	||||- span props.suffix 后缀
	||- hasDetails 存在详细描述
	|||- slots.details
	|||- hasCounter 存在计算器 > slots.counter 创建计算器


***