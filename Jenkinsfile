node {
   // Mark the code checkout 'stage'....
   stage 'Checkout'
   git url: 'https://github.com/jmalkic/test03.git'

   // Mark the code build 'stage'....
   stage 'Build'
   // Run the maven build
   sh "/usr/bin/mvn -Dmaven.test.failure.ignore clean package"
   step([$class: 'JUnitResultArchiver', testResults: '**/target/surefire-reports/TEST-*.xml'])
   
   stage 'Pack'
}
