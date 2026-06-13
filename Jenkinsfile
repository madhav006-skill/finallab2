pipeline {
agent any

tools {
    jdk 'JDK'
}

stages {

    stage('Checkout SCM') {
        steps {
            echo 'Checking out code...'
            checkout scm
        }
    }

    stage('Build') {
        steps {
            echo 'Building Project...'
            sh 'chmod +x gradlew'
            sh './gradlew clean build'
        }
    }

    stage('Test') {
        steps {
            echo 'Running Tests...'
            sh './gradlew test'
        }
    }

    stage('Run Application') {
        steps {
            echo 'Running Application...'
            sh './gradlew run'
        }
    }
}

post {
    always {
        echo 'Pipeline Finished!'
    }
    success {
        echo 'Build Successful '
    }
    failure {
        echo 'Build Failed '
    }
}

}
