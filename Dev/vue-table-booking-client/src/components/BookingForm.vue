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
            <input placeholder='Time' v-model='screeningTime'/>

            <label>Notes</label>
            <textarea placeholder='Add any special requests here' v-model='notes'/>

            <button type='submit'>Submit</button>
        </form>
    </div>
</template>

<script>
export default {
    // const ticketBatchLimit = 10
    // const ticketBatchOptions = () => {
    //     let options = []
    //     for ( let x=1; x <= ticketBatchLimit; x++) {
    //         options.push({ text: `${x}`, value: x })
    //     }
    //     return options
    // }

    name: 'bookingForm',
    data() {
        return {
            ticketBatchLimit: 10,
            numberOfTicketsOptions:[],
            screenTimes: [ '10:00', '10:30', '12:00', '13:00', '14:00', '18:00'],
            numberOfTickets: '1',
            date: '',
            screeningTime: '',
            notes: ''
        }
    },
    methods: {
        submit () {
            const { numberOfTickets, date, screeningTime, notes } = this
            localStorage.setItem('ticketRequest', JSON.stringify({
                numberOfTickets,
                date,
                screeningTime,
                notes 
            }))
        } 
    }
}
</script>

