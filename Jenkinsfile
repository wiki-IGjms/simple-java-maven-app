pipeline {
    agent {
        docker {
            image 'maven:3-alpine' 
            args '-v /root/.m2:/root/.m2' 
        }
    }
    stage('检出代码') {
            steps {
                checkout([$class: 'GitSCM',
                        branches: [[name: "master"]],
                        extensions: [],
                        url: "https://github.com/wiki-IGjms/simple-java-maven-app.git"]]])
            }
        }
    stages {
        stage('Build') { 
            steps {
                sh 'mvn -B -DskipTests clean package' 
            }
        }
    }
}
