pipeline{
    agent { label 'JDK11-MVN3.8.5-JAVA11' }

    triggers { 
        
        cron('45 23 * * *') 
        pollSCM('*/5 * * * 1-5') }
    
     stages{
        stage('SCM') {
            steps{
                git 'https://github.com/venkatareddymaram6/java11-examples.git'
                
                
            }

        }

            stage('build') {
            steps{
                 sh '/usr/local/apache-maven-3.8.5/bin/mvn clean package'
            }

        }
     }
}

