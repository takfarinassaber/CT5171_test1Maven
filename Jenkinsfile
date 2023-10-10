pipeline {
    agent any

    stages {
        stage ('GetProject') {
            steps {
                git 'https://github.com/takfarinassaber/CT5171_test1Maven.git'
            }
        }
        stage ('build') {
            steps {
                sh 'mvn clean:clean'
                sh 'mvn dependency:copy-dependencies'
                sh 'mvn compiler:compile'
            }
        }
//         stage ('Exec') {
//             steps {
//                 sh 'mvn exec:java'
//             }
//         }
        stage ('Package') {
            steps {
                sh 'mvn jar:jar'
            }
        }
    }
    post {
        always {
            archiveArtifacts allowEmptyArchive: true,
                artifacts: '**/ctCT5171_test1Maven*.jar'
        }
    }
}