node('JDK11-MVN3.8.4') {

    stage('git') {
        git 'https://github.com/venkatareddymaram6/java11-examples.git'
    
}
    stage('build'){
       sh 'mvn clen packae'
    }

    stage('archieve artifacts'){
     archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
    }
}