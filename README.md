# VueJs for test 

## memo

### watch vs computed
- vm > methods > watch = 호출 시마다
- vm > methods > computed = 캐시

### func in template
- {{function}} = computed = 캐시
- {{fucntion()}} = 캐시 X

### bind prop or on action
- v-bind:prop = :prop
- v-on:action = @action

### <template>
- 엘리먼트 추가하고 싶지 않을때

### v-if vs v-show
- v-if = 조건부 랜더링
- v-show = CSS toggle

### v-for의 :key
- 반복되는 DOM 내용이 단순한 경우나 의도적인 성능 향상을 위해 기본 동작에 의존하지 않는 경우를 제외하면, 가능하면 언제나 v-for에 key를 추가하는 것이 좋다


### 배열변경감지 > 변이메서드
호출된 원본 배열을 변형함:
- push()
- pop()
- shift()
- unshift()
- splice()
- sort()
- reverse()

#### 주의사항
1. 인덱스로 배열에 있는 항목을 직접 설정하는 경우, 예: vm.items[indexOfItem] = newValue
    - Vue.set(example1.items, indexOfItem, newValue)
example1.items.splice(indexOfItem, 1, newValue)

2. 배열 길이를 수정하는 경우, 예: vm.items.length = newLength
    - example1.items.splice(newLength)

### 객체변경감지 주의사항
속성 추가 및 삭제 감지 불가
```javascript
var vm = new Vue({
  data: {
    a: 1
  }
})
// `vm.a` 는 반응형입니다.

vm.b = 2
// `vm.b` 는 반응형이 아닙니다.
```
이렇게 해야함.
```javascript
Vue.set(object, key, value)
```

### keycode config
- Vue.config.keyCodes.f1 = 112

### 객체를 bind
```javascript
todo: {
  text: 'Learn Vue',
  isComplete: false
}
<todo-item v-bind="todo"></todo-item>

```
