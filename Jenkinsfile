pipeline{
    agent { label 'JDK11-MVN3.8.4' }
     triggers { 
       cron('45 11 * * 1-5') 
       upstream(upstreamProjects: 'started project', threshold: hudson.model.Result.SUCCESS)
         }
    
     stages{
        stage('SCM') {
            steps{
                git 'https://github.com/venkatareddymaram6/java11-examples.git'
            }

        }

            stage('build') {
            steps{
                 sh '/usr/local/apache-maven-3.8.4/bin/mvn clean package'
            }

        }
     }
}

