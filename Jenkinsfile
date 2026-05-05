pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/bharath442-dev/Jenkins-Project.git', branch: 'main'
            }
        }


        stage('Check GCC') {
    steps {
        bat 'where gcc'
    }
}

    stage('Build') {
    steps {
        bat '''
        if exist build rmdir /s /q build
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