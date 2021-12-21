pipeline
^
{
agent any {
  ^
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
}
}
