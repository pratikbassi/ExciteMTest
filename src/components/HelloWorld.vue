<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <Entry startDate="" endDate="" location="" @save="save" />
    <br/><br/><br/><br/>
    <ul >
      <li v-for="(item, index ) in locationList" :key="index">
        <br/>
        <Plan :location=item.location :startDate=item.startDate :endDate=item.endDate :position="index" @edit="edit" @delete="remove"></Plan>
      </li>
    </ul>
  </div>
</template>

<script>
import Entry from "@/components/Entry";
import Plan from "@/components/Plan";

export default {
  name: 'HelloWorld',
  data() {
    return {
      locationList:[],
    }
  },
  props: {
    msg: String
  },
  components: {
    Entry,
    Plan
  },
  methods: {
    save:function(e) {
      this.$data.locationList.push(e)
    },
    edit:function() {},

    remove:function(e) {
      this.$data.locationList.splice(e.position, 1)
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello{
  display: flex;
  flex-direction: column;
  align-items: center;
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}

a {
  color: #42b983;
}
</style>
