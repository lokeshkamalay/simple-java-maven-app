node('maven'){
    def mvnHome = tool name: 'maven360', type: 'maven'
    echo "downloading scm"
    stage('checkout'){
        git credentialsId: 'githubacc', url: 'https://github.com/ramharig/simple-java-maven-app.git'
    }
    stage('test'){
        echo "executing test caseds"
        sh "${mvnHome}/bin/mvn clean test surefire-report:report-only"
        archiveArtifacts 'target/surefire-reports/*'
        junit 'target/surefire-reports/*.xml'
        publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: 'target/site/', reportFiles: 'surefire-report.html', reportName: 'HTMLReport', reportTitles: ''])
    }
    stage ('build'){
        echo "build the package"
        sh "${mvnHome}/bin/mvn clean package -DskipTests=true"
    }
    stage('postbuild action'){
        echo "send notification to the user"
    }
}
