pipeline {

    agent any

  

    stages {

        stage('Build') {

            steps {

                echo "Build_stage"

                sh 'DOCKER_BUILDKIT=1 docker build -t tzivi-zalaznik/todo-fe:latest -f Dockerfile-pipeline --target builder .'

            }

        }

      

        stage('Test') {

            steps {

                echo "Test_stage"

                sh 'DOCKER_BUILDKIT=1 docker build -t tzivi-zalaznik/todo-fe:latest -f Dockerfile-pipeline --target testing .'

            }

        }




        stage('Delivery') {

            steps {

                echo "Delivery_stage"

                sh 'DOCKER_BUILDKIT=1 docker build -t tzivi-zalaznik/todo-fe:latest -f Dockerfile-pipeline --target delivery .'

            }

        }
        
        
        
         stage('Cleanup') {

            steps {

                echo "Cleanup_stage"

                sh 'docker system prune -f'

            }

        }
        stage('Push') {

            steps {

                echo "Push_stage"

                 sh 'docker login -u tzivya -p TZ621616@'
                sh 'docker push tzivya/todo-fe:latest'

            }

        }
       

                sh 'docker push efrat2020/todo-be:latest'

    }

}
