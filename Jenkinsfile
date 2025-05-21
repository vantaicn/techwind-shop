pipeline {
    agent any

    stages {
        stage('Check Tag') {
            when {
                expression {
                    return env.GIT_TAG_NAME?.startsWith('v') // chỉ chạy khi là tag
                }
            }
            steps {
                echo "Deploying release ${env.GIT_TAG_NAME}"
            }
        }

        stage('Build') {
            steps {
                sh 'npm install'
                sh 'npm run build'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying version ${env.GIT_TAG_NAME} to production"
                // Gọi shell script hoặc Ansible để deploy
            }
        }
    }
}
