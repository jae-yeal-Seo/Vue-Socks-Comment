<template>
  <div>
    <input type="text" v-model="user" />
    <input type="text" v-model="comment" />
    <button @click="save">Save</button><br />
    <ul>
      <li v-for="msg in message" :key="msg.comment">
        <p>{{ msg.user }}:{{ msg.comment }}</p>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      user: null,
      comment: null,
      message: [],
    };
  },
  methods: {
    save() {
      const message = {
        user: this.user,
        comment: this.comment,
      };
      //얜 객체구나.(message)

      if (message.user != null || message.comment != null) {
        this.message.unshift(message);
        this.user = null;
        this.comment = null;
        //데이터를 바꾸는게 v-model의 애들도 바꾸는 것이다.
      }
    },
  },
};
</script>
