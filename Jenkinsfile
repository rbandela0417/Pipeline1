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
                bat '''
                    
                    echo "M2 = %M2%"
                '''
            }
        }

        stage ('Build') {
            steps {
                    bat 'cd NumberGenerator & mvn install'
            }
             post {
                success {
                    junit 'NumberGenerator/target/surefire-reports/*.xml'
                        }
                 }
               

           
            }
        }
    
}
