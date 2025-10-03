pipeline {
   agent {
     label{
        label "built-in"
        customWorkspace "/root/2025-Q2"
    
     }

   }
    stages {
        stage ("create container c2"){
            steps {
                script {
                   sh '''
                    docker run -dp 90:80 --name c2 httpd 
                    '''
                }
            }
        }
        stage ("deploy index.html to c2 cont "){
            steps {
                script {
                   sh '''
                    docker cp index.html c2:/usr/local/apache2/htdocs
                    docker exec c2 chmod -R 755 /usr/local/apache2/htdocs/
                    '''
                }
            }
        }
    }
}
