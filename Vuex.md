# Vuex 知识点

### JS

```javasciprt
npm i -S vuex
import Vuex from 'vuex'
Vue.use(Vuex)

const store = new Vuex.Store({
	namespaced: true,
	state: {
		data: 'a'
	},
	mutations: {
		SET_DATA(state, data) {
			state.data = data
		}
	},
	actions: {
		setData({commit}, data) {
			commit('SET_DATA'，data)
		}
	},
	modules: {
		a: 'moduleA',
		b: 'moduleB'
	},
	getters: {}
})

export deault store

// store 方法
update('a') update('b') // 与 Vuex 中 modules 的 key 遥相呼应
update: ns => {
	// 传入的 module 的 key
	this.$store.dispatch(`${ns}/setData`, `${ns} a+`)
}
```

### HTML

```html
<div>{{ $store.state.a.data }}</div>
<div>{{ $store.state.b.data }}</div>
```