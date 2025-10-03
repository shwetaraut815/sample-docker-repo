pipeline {
   agent {
     label{
        label "built-in"
        customWorkspace "/root/2025-Q3"
    
     }

   }
    stages {
        stage ("create container c3"){
            steps {
                script {
                   sh '''
                    docker run -dp 8080:80 --name c3 httpd 
                   '''
                }
            }
        }
        stage ("deploy index.html to c3 "){
            steps {
                script {
                   sh '''
                    docker cp index.html c3:/usr/local/apache2/htdocs
                   '''
                }
            }
        }
    }
}
