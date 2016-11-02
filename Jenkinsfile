stage name:"Build and test"
node{
    git url: "https://github.com/caredotcom/hello"
    sh 'mvn clean package';
    archiveArtifacts artifacts: '**/target/*.war', fingerprint: true
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


