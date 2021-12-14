node('JDK11-MVN3.8.4') {

    properties([pipelineTriggers([upstream('started project, ')])])
    properties([pipelineTriggers([cron('0 */3 * * 0,6')])])

    stage('git') {
        git 'https://github.com/venkatareddymaram6/java11-examples.git'
    
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