<head>
  <link rel="stylesheet" href="app.css">
</head>

<script>
  let menuItems = [
    { name: 'Inicio', path: '/' },
    { name: 'Registro de Clientes', path: '/register' },
    
  ];
</script>

<nav>
  <ul>
    {#each menuItems as item}
      <li><a class="textoNav" href={item.path}>{item.name}</a></li>
    {/each}
    
  </ul>
</nav>
