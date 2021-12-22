pipeline
{
agent any 
 stages{
  
stage('Pull'){
steps{
script{
checkout ([$class: 'GitSCM' , branches: [[ name: '*/main' ]] ,
userRemoteConfigs: [[ 
credentialsId: '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' ,
url: 'https://github.com/akermiSafa/myapp.git']]])
}
}
}
stage('install') {
steps {
script{
sh " npm install --save-dev @angular-devkit/build-angular"
}
}
}

stage('Build'){
   steps{
    scripts{
     sh "ansible-playbook ansible/build.yml -i ansible/inventory/host.yml"
    }
   }
  }
  stage('docker') {
  steps{
  script{
  sh " ansible-playbook ansible/docker.yml -i ansible/inventory/host.yml " 
  }
  }
  }
  
}
}
