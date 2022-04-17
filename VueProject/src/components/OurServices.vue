<script>
export default
{
	props:
	{
		msg:
		{
			required: true,
			type: String
		}
	}
}
</script>

<template>
	<h1>Our Services</h1>
	<p>{{ msg }}</p>
</template>