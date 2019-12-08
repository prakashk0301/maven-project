pipeline{
agent any
{stages ('git clone')
{
steps
{git 'https://github.com/vwsk-private/maven-project.git'
}
}
}
{ stage ('compile code')
{ steps {
  withMaven(jdk: 'localjdk', maven: 'localmaven')
  { sh 'mvn compile'}}}
}
}
