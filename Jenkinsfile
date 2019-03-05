node('maven'){
    
    def maven360home = tool name: 'maven360', type: 'maven'
    
    stage('checkout'){
         git branch: 'Batch2', credentialsId: 'ProjectB', url: 'https://github.com/MNadir786/simple-java-maven-app.git'
    }
    
    
     stage('Building'){
        sh "$maven360home/bin/mvn clean package"
   

      
    }
}
