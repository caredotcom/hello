stage name:"Build and test"
node{
    checkout scm
    sh 'mvn clean package';
    archiveArtifacts artifacts: '**/target/*.war', fingerprint: true
}

if (env.BRANCH_NAME == 'master){
 echo 'In the master branch'
 stage name:"Special"
 node {
   echo 'I am special because I am master' 
 }
}
stage name:"Deploy"
node {
    echo 'Hello World'
    echo env.BUILD_NUMBER
    def sourceFile = env.WORKSPACE+"/target/hello.war";
    echo 'source is '+sourceFile;
    def moveCommand = 'mv '+sourceFile+' /usr/share/tomcat8/webapps/'
    sh moveCommand
}


