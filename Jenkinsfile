pipeline {
    agent any

    stages {
        stage('Check Tag') {
            when {
                expression {
                    return env.TAG_NAME?.startsWith('v') // chỉ chạy khi là tag
                }
            }
            steps {
                echo "Deploying release ${env.TAG_NAME}"
            }
        }

        stage('Build') {
            steps {
                echo "Building"
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying version ${env.TAG_NAME} to production"
            }
        }
    }
}
