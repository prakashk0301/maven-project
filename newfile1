pipeline{
agent any
{stages ('git clone')
{
steps
{git 'https://github.com/vaibhavkhilari/maven-project'
}
}
}
{ stage ('compile code')
{ steps {
  withMaven(jdk: 'localjdk', maven: 'localmaven')
  { sh 'mvn compile'}}}
}
}
