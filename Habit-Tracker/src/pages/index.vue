<template>
<v-text-field 
   hide-details="auto"
   label="Hours Worked"
   type="date"
   v-model="formData.date"
   >
</v-text-field>
<v-text-field 
   hide-details="auto"
   label="Hours Worked"
   v-model="formData.hours"
   >
</v-text-field>

<v-btn @click="submit">Add Entry</v-btn>

<v-card title="Habit Table">

    <v-data-table
    :items="items"
    ></v-data-table>
  </v-card>
</template>


<script lang="ts">

export default defineComponent({
    data: () => ({
        formData: {
            date: null,
            hours: null,
        },
        items:[
            
        ] as Object[]
    }),
    methods:{
        submit(){
           
            this.items.push(JSON.parse(JSON.stringify(this.formData)))
            console.log(this.items)
        
        }
    }
})



</script>
