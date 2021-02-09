pipeline {
  agent {
      any
    }
  }

  parameters {
    choice(
        name: 'Comando',
        choices: ['cat', 'wc'],
        description: 'Seleccione el ambiente composer sobre el cual se desea desplegar el DAG de prueba' )
    choice(
        name: 'Tecnologia',
        choices: ['folder01', 'folder02'],
        description: 'Seleccione la tecnologia que se desea testear' )  
  }
