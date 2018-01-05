node {
   // Mark the code checkout 'stage'....
   stage 'Checkout'
   
   //git url: 'https://github.com/TTFHW/jenkins_pipeline_java_maven.git'
   
   git url: 'https://github.com/jmalkic/test03.git'

   // Get the maven tool.
   // ** NOTE: This 'M3' maven tool must be configured
   // **       in the global configuration.           
   //def mvnHome = tool 'M3'

   // Mark the code build 'stage'....
   stage 'Build'
   // Run the maven build
   sh "/usr/bin/mvn -Dmaven.test.failure.ignore clean package"
   step([$class: 'JUnitResultArchiver', testResults: '**/target/surefire-reports/TEST-*.xml'])
   stage 'Pack'
}
