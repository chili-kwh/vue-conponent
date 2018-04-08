<template>
  <div>
    <div class="Input-Wrapper">
      <slot name="prepend"></slot>
      <input
        v-if="type === 'text'"
        class="Input"
        type="text"
        @input="handleInput"
        @keydown="handleKeyDown"
        :value="value"
        :placeholder="placeholder"
        :disabled="readonly"
        :maxlength="maxLength"
      />
      <textarea
        v-if="type === 'textarea'"
        class="Textarea"
        @input="handleInput"
        @keydown="handleKeyDown"
        :value="value"
        :placeholder="placeholder"
        :disabled="readonly"
        :maxlength="maxLength"
      />
    </div>
    <WingBlank v-if="env==='dev'">子组件inputValue:  {{value}}</WingBlank>
  </div>
</template>


<script>
  export default {
    name: 'Input',
    props: {
      type: {
        type: String,
        default: 'text'
      },
      value: {
        type: String,
        default: ''
      },
      placeholder: {
        type: String,
        default: '输入内容'
      },
      readonly: {
        type: Boolean,
        default: false
      },
      maxLength: {
        type: Number,
        default: null
      },
      env: {
        type: String,
        default: ''
      },
    },
    data() {
      return {}
    },
    methods: {
      handleInput(e) {
        this.$emit('input', e.target.value);
      },
      handleKeyDown(e) {
        if (e.keyCode === 13) {
          this.$emit('enter', e);
        }
      }
    },
    watch: {
      value(val) {
        this.$emit('change', val);
      }
    }
  }
</script>

<style>
  .Input-Wrapper {
    display: flex;
    padding: 16px;
    align-items: center;
    justify-content: space-between;
  }

  .Input {
    height: 36px;
    padding-left: 10px;
  }

  .Textarea {
    height: 100px;
    padding: 10px;
  }

  .Input, .Textarea {
    font-size: 16px;
    flex: 1;
    margin-left: 16px;
    border: 1px solid #f8f8f8;
  }

</style>
