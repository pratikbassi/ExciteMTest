<template>
  <div>
    <p>
      Location: {{location}}
    </p>
    <p>
      Start Date: {{startDate}}
    </p>
    <p>
      End Date: {{endDate}}
    </p>
    <button v-on:click="editEvent()">Edit</button>
    <button v-on:click="deleteEvent()">Delete</button>
  </div>
</template>

<script>
export default {
  name: "Plan",
  props: {
    startDate: String,
    endDate:String,
    location:String,
    position:Number
  },
  methods: {
    editEvent: function (){
      event.preventDefault();
      this.$emit("edit", {
        location:this.$props.location,
        startDate:this.$props.startDate,
        endDate:this.$props.endDate,
      })
    },
    deleteEvent: function (){
      event.preventDefault();
      this.$emit("delete", {
        position:this.$props.position
      })
    },
  }
}
</script>

<style scoped>
  div{
    background-color:lightcoral;
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    align-items: center;
    width:300px;
    height:300px;
  }

</style>