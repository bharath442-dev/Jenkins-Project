pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/bharath442-dev/Jenkins-Project.git', branch: 'main'
            }
        }

        stage('Build') {
            steps {
                bat '''
                mkdir build
                cd build
                cmake ..
                cmake --build .
                '''
            }
        }

        stage('Run') {
            steps {
                bat '''
                cd build
                dir
                '''
            }
        }
    }
}