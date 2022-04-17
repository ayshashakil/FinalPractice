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
	<h1>About Us</h1>
	<p>{{ msg }}</p>
</template>