pipeline {
    agent any

    tools {
        maven "MVN"
    }
    stages {
        stage('Build') {
            steps {
                println 'Cloning repository...'
                git 'https://github.com/acoppola2000/devopscon.git'
                println 'Starting the build...'
		sh "mvn clean install -Pci"
            }
            post {
                success {
                    junit '**/target/surefire-reports/TEST-*.xml'
                }
            }
        }
    }
}
