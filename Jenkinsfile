node ('master') {

  input 'Ready to go?'

  git url: 'https://github.com/Asp772/simple-maven-project-with-tests'

  def v = version()

  if (v) {
    echo "ALERT!Building version ${v}"
  }  

  def mvnHome = tool 'apache-maven-3.5.3'

  bat "${mvnHome}\\bin\\mvn -B verify"

}

def version() {
 
  def matcher = readFile('pom.xml') =~ '<version>(.+)</version>'

  matcher ? matcher[0][1] : null

}
