node('JDK11-MVN3.8.4') {

 properties([pipelineTriggers([upstream('starter-project')])])  
    stage('git') {
        git url: 'https://github.com/venkatareddymaram6/java11-examples.git', branch: "${params.BRANCH_TO_BUILD}"
    
}
    stage('build'){
       sh '/usr/local/apache-maven-3.8.4/bin/mvn clean package'
    }

    stage('archieve artifacts'){
     archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
    }

    stage('publishing test results'){

        junit '**/TEST-*.xml'
    }
}