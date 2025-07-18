pipeline {
  agent any

  stages {
    stage('Cloner le dépôt') {
      steps {
        git 'https://github.com/mickael2109/energy.git'
      }
    }

    stage('Construire les images Docker') {
      steps {
        sh 'docker-compose build'
      }
    }

    stage('Redémarrer les containers') {
      steps {
        sh 'docker-compose down && docker-compose up -d'
      }
    }
  }
}
