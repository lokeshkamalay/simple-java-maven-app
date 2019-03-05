node('maven'){
  def maven360home = tool name: 'maven360', type: 'maven'
    stage('checkout'){
        git branch: 'JenkinsPipeline', credentialsId: 'Pipeline', url: 'https://github.com/MNadir786/simple-java-maven-app.git'
    }
    stage('Building'){
        sh "$maven360home/bin/mvn clean package"
    }
    stage('Test Result'){
        junit 'target/surfire-reports/*.xml'
    }
    stage(Archive Artifcats'){
          archiveArtifacts '**/target/*.jar'
          }
          }
          
