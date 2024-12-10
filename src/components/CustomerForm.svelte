<head>
  <link rel="stylesheet" href="app.css">
</head>

<script>
  let cliente = '';
  let cif = '';
  let contacto = '';
  let telefono = '';
  let email = '';
  let direccion = '';

  function Guardar() {
    console.log('Datos guardados', { cliente, cif, contacto, telefono, email, direccion });
    alert('Cliente guardado correctamente');

    // Limpiar los campos del formulario
    cliente = '';
    cif = '';
    contacto = '';
    telefono = '';
    email = '';
    direccion = '';
  }

  function Cancelar() {
    console.log('Operación cancelada');
    alert('Cliente Cancelado');
    
    // Limpiar los campos del formulario
    cliente = '';
    cif = '';
    contacto = '';
    telefono = '';
    email = '';
    direccion = '';
  }
</script>



<form class="formulario" on:submit|preventDefault={Guardar}>

  <button class="nuevocliente" type="submit">NUEVO CLIENTE</button>

  <div class="form-group">
    <label for="cliente">SELECCIONAR CLIENTE:</label>
    <input id="cliente" bind:value={cliente} placeholder="Listado Clientes" required>
  </div>
  
  <div class="guiones">
    <label for="guiones">---------- o ----------</label>
  </div>

  <div class="form-group">
    <label for="cif">CIF:</label>
    <input id="cif" bind:value={cif} required>
  </div>

  <div class="form-group">
    <label for="contacto">CONTACTO:</label>
    <input id="contacto" bind:value={contacto} required>
  </div>

  <div class="form-group">
    <label for="telefono">TELÉFONO:</label>
    <input id="telefono" type="tel" bind:value={telefono} required>
  </div>

  <div class="form-group">
    <label for="email">EMAIL:</label>
    <input id="email" type="email" bind:value={email} required>
  </div>

  <div class="form-group-direccion">
      <label for="direccion">DIRECCION:</label>
      <input id="direccion" bind:value={direccion} required>
  </div>

  <div class="button-container">
    <button type="submit">GUARDAR</button>
    <button type="button" on:click={Cancelar}>CANCELAR</button>
  </div>

</form>
