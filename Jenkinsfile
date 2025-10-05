pipeline {
   agent {
     label{
        label "built-in"
        customWorkspace "/root/2025-Q1"
    
     }

   }
    stages {
        stage ("create container c1"){
            steps {
                script {
                   sh '''
                    docker run -dp 80:80 --name c1 httpd 
                   '''
                }
            }
        }
        stage ("deploy index.html to c1 container "){
            steps {
                script {
                   sh '''
                    docker cp index.html c1:/usr/local/apache2/htdocs
                    docker exec c1 chmod -R 755 /usr/local/apache2/htdocs/
                   '''
                }
            }
        }
    }
}
