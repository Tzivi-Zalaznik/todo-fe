pipeline {

    agent any

  

    stages {

        stage('Build') {

            steps {

                echo "Build_stage"

                sh 'DOCKER_BUILDKIT=1 docker build -t Tzivi-Zalaznik/todo-fe:latest --target Build .'

            }

        }

      

        stage('Test') {

            steps {

                echo "Test_stage"

                sh 'DOCKER_BUILDKIT=1 docker build -t Tzivi-Zalaznik/todo-fe:latest --target Test .'

            }

        }




        stage('Delivery') {

            steps {

                echo "Delivery_stage"

                sh 'DOCKER_BUILDKIT=1 docker build -t Tzivi-Zalaznik/todo-fe:latest --target Delivery .'

            }

        }
        
        
        
         stage('Cleanup') {

            steps {

                echo "Cleanup_stage"

                sh 'docker system prune'

            }

        }
        stage('Push') {

            steps {

                echo "Push_stage"

                sh 'docker push tzivya/todo-fe:latest'

            }

        }

    }

}
