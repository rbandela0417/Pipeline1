pipeline {
    agent {
        label "master"
    }
    tools {
        maven 'maven 1'
        jdk 'JAVA_HOME'
    }
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    
                    echo "M2 = %M2%"
                '''
            }
        }

        stage ('Build') {
            steps {
                    sh 'cd NumberGenerator & mvn install'
            }
             post {
                success {
                    junit 'NumberGenerator/target/surefire-reports/*.xml'
                        }
                 }
               

           
            }
        }
    
}
