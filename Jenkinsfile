node('maven'){
    
    def maven360home = tool name: 'maven360', type: 'maven'
    
    stage('checkout'){
        git branch: 'batch2', credentialsId: 'NAWAB786', url: 'https://github.com/MNadir786/simple-java-maven-app.git'
    }
    
    
    stage('Running Tests'){
        sh "$maven360home/bin/mvn clean test surefire-report:report-only"
        junit allowEmptyResults: true, testResults: 'target/surefire-reports/*.xml'
    }
        stage('Building'){
           sh "$maven360home/bin/mvn clean package"
    }
    
   // stage('Executing Test Cases'){
   //     echo "Executing Test Cases Started"
     //   sh "$maven360home/bin/mvn clean test surefire-report:report-only"
     //   archivesArtifacts 'target/**/*/'
     //   junit allowEmptyResults: true, testResults: 'target/surefire-reports/*.xml'
       // publishHTML(allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: 'target/site', reportFiles: 'surefire-report
       // echo " Executing Test Cases Completed "
    }
  
    stage('Archive Artifacts'){
        archiveArtifacts '**/target/*.jar'
    }
    
    
    }
}
