<template>
    <div>
        <h1>Book Cinema Tickets</h1>
        <form @submit='submit'>
            <label>Number of Tickets</label>
            <select v-model='numberOfTickets'>
                   <option v-for='option in numberOfTicketsOptions' :value='option.value'>
                        {{ option.text }}
                    </option>
            </select>
                        
            <label>Date</label>
            <input placeholder='Date' v-model='date'/>

            <label>Screening</label>
            <select v-model='screeningTime'>
                   <option v-for='option in screenTimesOptions' :value='option.value'>
                        {{ option.text }}
                    </option>
            </select>

            <label>Notes</label>
            <textarea placeholder='Add any special requests here' v-model='notes'/>

            <button type='submit'>Submit</button>
        </form>
    </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const numberOfTickets = ref(1)
const date = ref('')
const screeningTime = ref('')
const notes = ref('')

const ticketBatches = ['1', '2', '3', '4', '5']
const numberOfTicketsOptions = getSelectOptionsForList(ticketBatches)
const screenTimes = [ '10:00', '10:30', '12:00', '13:00', '14:00', '18:00']
const screenTimesOptions = getSelectOptionsForList(screenTimes)

function getSelectOptionsForList (options) {
    return options.map( o => ({ text: o.toString(), value: o }))
}

function submit() {
    ('Form submitted!')    
    // localStorage.setItem('ticketRequest', JSON.stringify({
    //     numberOfTickets,
    //     date,
    //     screeningTime,
    //     notes 
    // }))
} 

onMounted(() => {
    console.log(date)
})
</script>

