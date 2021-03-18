<template>
  <div >
    <form>
      <label>
        Destination
        <input v-model="location" required/>
      </label>
      <label>
        Start Date
        <input v-model="startDate" type="date" required/>
      </label>
      <label>
        End Date
        <input v-model="endDate" type="date" required/>
      </label>
      <button v-on:click="saveMethod($event)">Save</button>
    </form>

  </div>
</template>

<script>
export default {
  name: "Destination",

  data() {
    return {
      location:"",
      startDate:"",
      endDate:"",
    }
  },
  methods: {
    saveMethod:function (event){
      event.preventDefault();
      this.$emit("save", {
        location:this.$data.location,
        startDate:this.$data.startDate,
        endDate:this.$data.endDate,
      })
      this.$data.startDate = ""
      this.$data.endDate = ""
      this.$data.location = ""

    }
  },

}
</script>

<style scoped>
  form{
    padding:5px;
    background-color: lightgray;
    width: 300px;
    height: 200px;
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    align-items: center;
  }


</style>