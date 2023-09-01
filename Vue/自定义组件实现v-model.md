## 父子组件双向绑定v-model

1. 非表单元素使用自定义v-model进行双向绑定传值
<!-- 父组件 -->
<template>
  <div>
    <son v-model="value"></son>
  </div>
</template>

<script>
import son from '@/components/son.vue';

export default {
  data () {
    return {
      value: '父子组件双向绑定v-model'
    }
  },
  components: {
    son
  },
  watch: {
    value ( nv, ov ) {
      console.log(nv, ov)
    }
  }
};
</script>
<!-- 子组件 -->
<template>
  <div>
    <p>{{ value }}</p>
  </div>
</template>

<script>
export default {
  model: {
    prop: 'value',
    event: 'value-event'
  },
  props: {
    value: {
      type: String,
      default: ''
    }
  },
  mounted () {
    setTimeout(() => {
      let newValue = 'new value'
      this.$emit('value-event', newValue)
    },3000)
  }
}
</script>

2. 表单元素input，radio等监听表单的input或者change事件，或者直接利用原始原素的v-model，实时将value或者checked通过$emit传递
<!-- 父组件 -->
<template>
  <div>
    <son v-model="value"></son>
  </div>
</template>

<script>
import son from '@/components/son.vue';

export default {
  data () {
    return {
      value: '父子组件双向绑定v-model'
    }
  },
  components: {
    son
  },
  watch: {
    value ( nv, ov ) {
      console.log(nv, ov)
    }
  }
};
</script>
<!-- 子组件 -->
<template>
  <div>
    <h1>子组件</h1>
    <input type="text" v-model="newValue">
  </div>
</template>

<script>
export default {
  props: {
    value: {
      type: String,
      default: ''
    }
  },
  computed: {
    newValue: {
      get () {
        return this.value
      },
      set (val) {
        this.$emit('input', val)
      }
    }
  }
}
</script>