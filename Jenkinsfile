pipeline {
    agent{
        label 'ansible'
    }
    stages{
        stage('checkout git'){
            steps{
                git branch: 'main', credentialsId: '23920420-e23b-464e-ba4a-bdc56cec9944', url: 'git@github.com:kostidan/mnt-homeworks-ansible.git'
            }
        }
        stage('install dependencies'){
            steps{
                sh 'pip3 install -r test-requirements.txt'
            }
        }
        stage('run molecule'){
            steps{
                sh 'molecule test'
            }
        }
    }
}