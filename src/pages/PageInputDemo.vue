<template>
  <div>
    <Whitespace>type="text"</Whitespace>
    <Input
      type="text"
      v-model="inputValue1"
      placeholder="set placeholder"
      :maxLength='6'
      @change="handleChange"
      @enter="handleEnter"
      env="dev"
    >
    <div slot='prepend'>prepend</div>
    </Input>
    <WingBlank>父组件inputValue:  {{inputValue1}}</WingBlank>
    <WingBlank>
      <div @click="addValue">点击通过父组件更改子组件value</div>
    </WingBlank>
    <Whitespace>type="text" disable</Whitespace>
    <Input
      type="text"
      value="readonly"
      :readonly="true"
      placeholder="set placeholder"
    >
    <div slot='prepend'>prepend</div>
    </Input>
    <Whitespace>type="textarea"</Whitespace>
    <Input
      type="textarea"
      placeholder="set placeholder"
      v-model="inputValue2"
      :maxLength='6'
    >
    <div slot='prepend'>prepend</div>
    </Input>

    <br/>
  </div>
</template>

<script>
  import Input from './../components/Input'


  export default {
    name: 'InputDemo',
    components: {
      Input,
    },
    data() {
      return {
        inputValue1: '',
        inputValue2: '',
      }
    },
    methods: {
      addValue() {
        this.inputValue1 += 1;
      },
      handleChange(val) {
        console.log(`InputChange: ${val}`)
      },
      handleEnter() {
        console.log(`onEnter`)
      },
    }
  }
</script>
