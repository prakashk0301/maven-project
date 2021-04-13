pipeline
{
agent any
stages
{
  stage('scm checkout')
  { steps {  git branch: 'master', url: 'https://github.com/prakashk0301/maven-project'  } }

  stage('code build')
  { steps {  withMaven(jdk: 'local_jdk', maven: 'local_maven') {
      sh 'mvn clean package'                    // provide maven command

} } }


  stage('deploy to dev')
    { steps {
       sshagent(['tomcat-host2']) {
       sh 'scp -o StrictHostKeyChecking=no */target/*.war  ec2-user@172.31.3.245:/usr/share/tomcat/webapps'
    }
            }
         }

}
}
