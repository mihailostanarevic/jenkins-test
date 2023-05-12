pipeline {
    agent any
    stages {
        stage ("Clean Up") {
            steps {
                deleteDir()
            }
        }
        stage("Clone Repo") {
            steps {
                bat "git clone https://github.com/mihailostanarevic/jenkins-test"
            }
        }
        stage("Build and run tests") {
            steps {
                dir("jenkins-test") {
                    bat "mvn clean install"
                }      
            }
        }
        stage('master-branch-stuff') {
            when {
                branch 'main'
            }
            steps {
                echo 'This is the main branch'
            }
        }
    }
}