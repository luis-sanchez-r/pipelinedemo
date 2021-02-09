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

  stages {
      stage('Comando a ejecutar') {
          steps {
              git clone https://github.com/luis-sanchez-r/pipelinedemo.git
              cd pipelinedemo
              echo " El comando a ejecutar es ${params.Comando} en el folder ${params.Tecnologia}"
              ${params.Comando} ${params.Tecnologia}/file01.prf
          }
      }
  }
