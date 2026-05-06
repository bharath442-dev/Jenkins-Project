pipeline {
    agent any

    environment {
        PATH = "C:\\msys64\\mingw64\\bin;${env.PATH}"
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/bharath442-dev/Jenkins-Project.git'
                bat 'git submodule update --init --recursive'
            }
        }

        stage('Check GCC') {
            steps {
                bat 'gcc --version'
                bat 'g++ --version'
                bat 'mingw32-make --version'
            }
        }

        stage('Build') {
            steps {
                bat 'if exist build rmdir /s /q build'
                bat 'mkdir build'
                bat 'cd build && cmake .. -G "MinGW Makefiles" -DCMAKE_C_COMPILER=C:/msys64/mingw64/bin/gcc.exe -DCMAKE_CXX_COMPILER=C:/msys64/mingw64/bin/g++.exe'
                bat 'cd build && mingw32-make'
            }
        }

        stage('Test') {
            steps {
                bat 'cd build\\test && ExampleTests.exe'
            }
        }

    }

    post {
        success {
            echo "BUILD SUCCESS ✅"
        }
        failure {
            echo "BUILD FAILED ❌"
        }
    }
}