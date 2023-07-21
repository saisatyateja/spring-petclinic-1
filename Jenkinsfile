pipeline{
    agent any
    stages{
        stage("source code"){
            steps{
                git url:"https://github.com/saisatyateja/spring-petclinic-1.git",
                    branch:"main"
            }
        }
        stage('build')  {
            steps {
                sh 'mvn  package'
            }
        }
        stage('test results') {
            steps {
               junit '**/surefire-reports/*.xml'
            }
        }
        stage('archive artifacts') {
            steps {
                archiveArtifacts '**/target/*.jar'
            }
        }  
        stage('deploy'){
            steps{
                sh "java -jar spring-*.jar" 
            }
        } 
    }
}