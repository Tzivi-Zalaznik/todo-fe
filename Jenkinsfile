pipeline {

    agent any

  

    stages {

        stage('Build') {

            steps {

                echo "Build_stage"

                sh 'DOCKER_BUILDKIT=1 docker build -t tzivya:latest --target Build .'

            }

        }

      

        stage('Test') {

            steps {

                echo "Test-stage"

                sh 'DOCKER_BUILDKIT=1 docker build -t tzivya:latest --target Test .'

            }

        }




        stage('Delivery') {

            steps {

                echo "Delivery-stage"

                sh 'DOCKER_BUILDKIT=1 docker build -t tzivya:latest --target Delivery .'

            }

        }

    }

}
