<script>
	import Mensaje from "./Mensaje.svelte";
	let mensajes = ["hola", "hello", "bonjour"];
	let textoInput="";
	const mandarMensaje = () => {
		console.log(textoInput);
	//	mensaje.push(textoInput);
		mensajes = [...mensajes, textoInput];
		textoInput="";
	};
</script>

<p>IRC chat</p>
{#each mensajes as mensaje}
<Mensaje {mensaje}/>
{/each}

<form on:submit|preventDefault={mandarMensaje}>
	<input type="text" bind:value={textoInput}/>
	<input type="submit"/>
</form>