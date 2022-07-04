pipeline {
    agent any
    stages {
        stage ('Deploy Secrets') {
            steps {
                sh ''' sudo -H -u i21177 bash -c 'kubectl apply -f /mnt/c/Database-Tier/mysql-secret.yaml' '''
            }
        }
        stage ('Deploy Database') {
            steps {
                sh ''' sudo -H -u i21177 bash -c 'kubectl apply -f /mnt/c/Database-Tier/mysqldeployment.yaml' '''
                sh ''' sudo -H -u i21177 bash -c 'kubectl apply -f /mnt/c/Database-Tier/mysqlservice.yaml' ''' 
            }
        }
    }

}