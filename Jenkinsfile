pipeline {
    agent any
    stages {
        stage ('Deploy Secrets') {
            steps {
                sh ''' sudo -H -c i21177 bash -c 'kubectl apply -f /mnt/c/Database-Tier/mysql-secret.yaml' '''
            }
        }
        stage ('Deploy Application') {
            steps {
                sh ''' sudo -H -c i21177 bash -c 'kubectl apply -f /mnt/c/Database-Tier/mysqldeployment.yaml' '''
                sh ''' sudo -H -c i21177 bash -c 'kubectl apply -f /mnt/c/Database-Tier/mysqlservice.yaml' ''' 
            }
        }
    }

}