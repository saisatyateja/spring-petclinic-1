pipeline{
    agent{
        label "node1"
    }
    stages{
        stage("source code"){
            steps{
                git url:"",
                    branch:""
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