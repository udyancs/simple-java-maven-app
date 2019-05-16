pipeline {
    agent {
        docker {
            image 'maven:3-alpine'
            args '-v /root/.m2:/root/.m2'
        }
    }
    stages {
        stage('Build') {
            steps {
                script {
                    currentBuild.displayName = ${BRANCH_NAME}
                    currentBuild.description = "The best description."
                }
                sh 'mvn -B -DskipTests clean package'
            }
        }
    }
}
