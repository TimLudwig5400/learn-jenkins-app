pipeline {
    agent any

    stages {
      
            stage('Test') {
                 agent{
                docker{
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
                steps {
                    sh '''
                    test -f build/index.html
                    npm test
                    '''
                }
            }
        }

        post{
            always{
                junit 'test-results/junit.xml'
            }
        }
    }
