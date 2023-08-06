<script>
  let nombre = 'Diego';
  let v1= 0 ;
  let v2=0;
  let check = false;
  function alerta1(){
    alert('Alerta 1');
  }
  const alerta2 = ()=>alert('Alerta 2');
  let contador=0;
  $: resultado = contador *10; // para crear una variable reactiva se hace con el simpolo $: adelante

  let texto = '';
  $: if(resultado ===30){
    texto ='OK 😃'
  }
  else{
    texto ='Ooouch 😢';
  }
</script>

<main>
  <head>
  <link
    href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css"
    rel="stylesheet"
  />
</head>
  <h1>DATABINDING</h1>
  <h2>{nombre}</h2>
  <input type = "text" bind:value={nombre}>
  <hr>
  valor 1  <input type = "range" bind:value={v1}>
  valor 2  <input type = "range" bind:value={v2}>
  <p>{v1} + {v2} ={v1 + v2} </p>
  <hr>
  Habilitar Botón <input type = 'checkbox' bind:checked={check} >
  <button disabled={!check}>Guardar</button>
  <hr>

  <h1>ON CLICK 🤩😘 </h1>

  <button on:click={alerta1} >Alerta 1</button>
  <button on:click={alerta2} >Alerta 2</button>
  <hr>
  <h1>VARIABLES REACTIVAS</h1>
  <button on:click={ ()=> contador +=1 }>Contador</button>
  <p> contador = {contador}</p>
  <p> Variable Reactiva Resultado x 10  = {resultado}</p>
  <p>{texto}</p>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}
  h2{
    color:red;
  }
  p{
    padding:1em;
    color:blue;
  }
	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>
<!-- Agrega el siguiente import de Bootstrap -->
<link
  href="node_modules/bootstrap/dist/css/bootstrap.min.css" rel="stylesheet"
/>