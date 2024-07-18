pipeline {
    agent any
    stages {

        stage('Installing Ansible') {
            steps {
                script {
                    def ansible_exists = fileExists '/usr/bin/ansible'

                    if (ansible_exists == true) {
                        echo "Skipping Ansible install - already exists"
                    } else {
                        sh 'sudo apt-get update -y && sudo apt-get upgrade -y'
                        sh 'sudo apt install -y wget tree unzip ansible python3-pip python3-apt'
                    }
                }
            }
        }

        stage('Delete the workspace') {
            steps {
                cleanWs()
            }
        }

        stage('Second Stage') {
            steps {
                echo "Second stage"
            }
        }

        stage('Third Stage') {
            steps {
                echo "Third stage"
            }
        }
    }
}