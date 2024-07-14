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
}
}
stages{
stage('build'){
steps{
echo 'building worker app'
dir('worker'){
sh 'mvn compile'
}
}
}
stage('test'){
steps{
echo 'running unit tests on worker app'
dir('worker'){
sh 'mvn clean test'
}
}
}
stage('package'){
steps{
echo 'packaging worker app into a jarfile'
dir('worker'){
-- INSERT --                                                                                 1,1           Top
