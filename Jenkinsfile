pipeline {
  agent any
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
  environment {
    def RUN_ID = sh(script: "echo `date +%Y%m%d%H%M%S`", returnStdout: true).trim()
  }
  stages {
      stage('Comando a ejecutar') {
          steps {
            sh 'rm -fr pipelinedemo'
            sh 'git clone https://github.com/luis-sanchez-r/pipelinedemo.git'
            sh 'cd pipelinedemo'
            sh "echo \"El comando a ejecutar es ${params.Comando} en el folder ${params.Tecnologia}\" "
            sh "${params.Comando} ${params.Tecnologia}/file01.prf"
            sh "echo el run_id es: ${RUN_ID}"
          }
      }
    }
  }
