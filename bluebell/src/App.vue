
<template>
  <h3>你好，vue\n</h3>
  <p>{{ msg }}</p>
  <p>{{ hello }}</p>
  <p>{{ number +1}}</p>
  <p>{{ message.split("").reverse().join("")}}</p>
</template>

<script>
export default {
  data() {
    return {
      msg: "神奇的语法",
      hello: "hello world",
      number: 1,
      message: "你好打卡时间法律肯德基"
    }
  }
}

</script>
