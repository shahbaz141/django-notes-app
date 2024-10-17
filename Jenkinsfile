@Library("shared") _
pipeline {
    agent { label "ferry" } // Removed colon after "label"
    
    stages {
        stage("hello"){
            steps{
                script{
                    hello()
                }
            }
        }
        stage("code") { // Quoted stage name
            steps {
                script{
                    gitClone("https://github.com/shahbaz141/django-notes-app.git","main")
                }
            }
        }
        stage("build") { // Quoted stage name
            steps {
                script{
                    build()
                }
            }
        }
        stage("push to dockerhub"){
            steps{
                script{
                    loginDockerPush("dockercred")
                }
            }
      }
        
        stage("test") { // Quoted stage name
            steps {
                echo "Testing will start soon"
            }
        }
        stage("deploy") { // Quoted stage name
            steps {
              script{
                  containerdown()
                  deploy()
              }
            }
        }
    }
}
