stage('vote integration'){
agent any
when{
changeset "**/vote/**"
branch 'master'
}
steps{
echo 'Running Integration Tests on vote app'
dir('vote'){
sh 'sh integration_test.sh'
}
}
}
