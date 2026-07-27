pipeline{
  agent any
  environment {
    MY_SECRET = credentials("test-secret")
  }
  stages {
    stage("Checkout Info") {
      steps {
        echo "Code already checkout by Jenkins Pipeline"
      }
    }
    stage("Run Script"){
      steps {
        sh "chmod +x greet.sh"
        sh "./greet.sh"
      }
    }
    stage("Test"){
      steps{
        sh 'echo "Running a fake test..."'
        sh "test 1 -eq 1"
      }
    }
    stages("Use Secret") {
      steps {
        sh 'echo "Using secrets now..."'
        sh "echo $MY_SECRET"
      }
    }
  }
}
