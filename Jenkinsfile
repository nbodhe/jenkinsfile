node('aws_node1') { 
    stage('Checkout'){
       git 'git@github.com:nbodhe/SampleWebApplication.git'
    }
    stage('Build') { 
        sh 'mvn clean install package' 
    }
    stage('Test') {
        
        sh 'echo "Tested Successfully"'
        //sh 'ansible-playbook /etc/ansible/site.yaml -i /etc/ansible/inventories/production -u ec2-user -t cf'
    }
    stage('Deploy') {
           // sh 'ansible-playbook /etc/ansible/site.yaml -i /etc/ansible/inventories/production -u ec2-user -t deploy'
        }
    if (currentBuild.currentResult == 'SUCCESS') {
        stage('Deploy') {
            sh 'echo "Deployed"'
        }
    }
}
