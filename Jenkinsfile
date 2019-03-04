node('maven'){
    def maven360Home = tool name: 'maven360', type: 'maven'
    stage('checkout'){
    git branch: 'batch2', credentialsId: 'MavenBuild', url: 'https://github.com/MNadir786/simple-java-maven-app.git'
    }
    
    stage('Building'){
        sh "$maven360home/bin/mvn clean package"
    }
    
}
