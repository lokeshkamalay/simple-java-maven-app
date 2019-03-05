node('maven'){
    def maven360home = tool name: 'maven360', type: 'maven'
    stage('checkout'){
        echo "Checking the Git code"
     git branch: 'JenkinsPipeline', credentialsId: 'MavenBuild', url: 'https://github.com/MNadir786/simple-java-maven-app.git'
    }
    stage('Building'){
        echo "Adding new lines"
        sh "$maven360home/bin/mvn clean package"
    }
}

  
