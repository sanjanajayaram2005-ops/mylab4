pipeline{
  agent any

  tools{
    mvn 'Maven'
  }
  stages
  {
    stage ("Checkout")
    {
      steps {
      git 'https://github.com/sanjanajayaram2005-ops/mylab4.git'
      }
    }
    stage ("Build")
    { 
      steps {
      sh 'mvn clean install'
      }
    }
    stage ("Create source file")
    {
      steps {
        sh 'echo "This data will be copied!"> source.txt'
      }
    }
    stage ("Run Application")
    {
      steps {
        sh 'mvn exec:java -Dexec.mainClass="com.example.App"'
      }
    }
    stage ("Verify output")
    {
      steps {
        sh 'cat destination.txt'
      }
    }
  }
}
