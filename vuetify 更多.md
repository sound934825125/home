## Features Aliasing

创建别名，以 Vuetify 组件作为基础，扩展自定义组件。

	import { createVuetify } from 'vuetify'
	import { VBtn } from 'vuetify/components'

	export default createVuetify({
	  aliases: {
	    MyButton: VBtn,
	    MyButtonAlt: VBtn,
	  },
	  defaults: {
	  	VBtn: { variat: 'flat' },
	  	MyButton: { variat: 'tonal' }
	  	VCard: { 
	  		MyButton: { color: 'secondary' },
	  		VBtn: { color: 'primary' }
	  	}
	  }
	})

`defaults` 选项更改组件或自定义组件默认值。	

## less sass 支持

	$ npm install -D sass-loader sass