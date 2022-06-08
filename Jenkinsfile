node('JDK11-MVN3.8.5-JAVA11') {

 properties([pipelineTriggers([upstream('starter-project')])])  
    stage('git') {
         git branch: 'scripted', url: 'https://github.com/venkatareddymaram6/java11-examples.git'
    
}
    stage('build'){
       sh '/usr/local/apache-maven-3.8.5/bin/mvn clean package'
    }

    stage('archieve artifacts'){
     archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
    }

    stage('publishing test results'){

        junit '**/TEST-*.xml'
    }
}