pipeline{
  agent any
  stages{
    stage('git-clone'){
        steps{
            checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-id', url: 'https://github.com/Stha-Rog/parallel-test.git']]])
        }
    }
    stage('parallel-job'){
      parallel{
        stage('sub-job1'){
          steps{
            echo "sub-job1 task"
          }
        }
        stage('sub-job2'){
          steps{
            echo "sub-job2 task"
          }
        }
        stage('sub-job3'){
            steps{
                echo "sub-job3 task"
            }
        }
      }
    }
    stage('version-check'){
        steps{
            echo "end of parallel-job"
        }
    }
  }
}