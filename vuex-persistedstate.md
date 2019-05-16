页面刷新后 想保存页面未保存的数据  我们总是习惯放在localStorage和sessionStorage中  但是用了vue后 vuex便可以被应用了
vuex优势  相比sessionStorage 存储数据更安全 sessionStorage可以在控制台被看到
vuex劣势 在F5刷新页面后 vuex会重新更新state  所以 存储数据会丢失

原理：
	将vuex的state存在localStorage或sessionStorage或cookie中一份
	刷新页面的一瞬间 vuex数据消失 vuex回去sessionStorage中拿回数据 变相的实现了数据刷新不丢失
	
	使用的时候记得加plugins:[此处为引入vuex-persistedstate的名字]
	
使用方法
import createPersistedState from "vuex-persistedstate"
const store = new Vuex.Store({
  // ...
  plugins: [createPersistedState()]
})