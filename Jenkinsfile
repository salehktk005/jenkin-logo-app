pipeline {
    agent any

    stages{
        stage("build"){
            agent{
                docker{
                    image "node:18-alpine"
                    reuseNode true
                }
            }
        }
        stage("test"){
            steps{
                sh '''
                  test -f build/index.html
                '''
            }

            steps{
                sh '''
                 ls -la
                 node --version
                 npm --version
                 npm ci
                 npm run build
                 ls -la
                '''
            }
        }
    }       
}
