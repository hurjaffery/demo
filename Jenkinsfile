flag = true
pipeline {
agent any
stages {
stage('Build') {
steps {
echo 'Building Project'
// Here you can define commands for your build
}
}
stage('Test') {
steps {
  when { 
    expression {
      flag ==false
    }
  }
echo 'Testing Project'
// Here you can define commands for your tests
}
}
stage('Deploy') {
steps {
echo 'Deploying....'
// Here you can define commands for your deployment
}
}

}
  post{
    always{
      echo'Post Build condition running'
    }
    failure{
      echo'Post action if build faild'
    }
  }
}
