<script>
import { format } from 'date-fns'
import OurCustomers from './components/OurCustomers.vue'
import AboutUs from './components/AboutUs.vue'
import OurServices from './components/OurServices.vue'

const API_URL = "https://api.openweathermap.org/data/2.5/weather?&q=paris,ca&units=metric&appid=349d277757ae7960bc9cebc78b96541f"

export default
{
  data()
  {
    return{ date: format(new Date(), 'yyyy-MM-dd HH:mm:ss'), weather: "Loading" }
  },

  created()
	{
		this.fetchData()
	},
	
	methods:
	{
		async fetchData()
		{
			var weather_data = await(await(fetch(API_URL))).json()
			this.weather = weather_data.main.temp + " degrees Celcius"
		}
	},

	components:
	{
		AboutUs,
		OurCustomers,
		OurServices
	}
}

</script>

<template>
  <p> Date: {{ date }}</p>
  <p> Weather in Paris, ON: {{ weather }}</p>
  <OurCustomers />
  <AboutUs msg="HELLO" />
  <OurServices msg="HIHIHI" />
</template>

