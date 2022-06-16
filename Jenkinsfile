node('maven') {
    stage('git'){
      git branch: 'script', credentialsId: 'MAVEN_NODE', url: 'https://github.com/siva-pra/spring-boot-maven-example-helloworld-upstream.git'
    }
    stage('build'){
        sh 'mvn clean package'
    }
    stage('archive artifacts'){
        archiveArtifacts artifacts: 'target/*.jar',followSymlinks: false
    }
    stage('test result'){
        junit '**/TEST-*.xml'
    }
} 