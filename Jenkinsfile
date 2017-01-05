node {
    // Get the maven tool.
    // ** NOTE: This 'M3' maven tool must be configured
    // **       in the Jenkins global configuration.
    def mvnHome = tool 'M3'
    sh "echo ${mvnHome}"
    
    
    // Mark the code checkout 'stage'....
    stage 'Checkout'
    // Get some code from a GitHub repository
    checkout scm    
   
    // Mark the code build 'stage'....
    stage 'Build DME'
    // Run the maven build
    //sh for unix bat for windows
	
    sh "${mvnHome}/bin/mvn -f scld-config-api/pom.xml clean install -DskipTests=true"
    sh "${mvnHome}/bin/mvn -f dme2-schemas/pom.xml clean install -DskipTests=true"
    sh "${mvnHome}/bin/mvn -f dme3-base/pom.xml clean install -DskipTests=true"
    sh "${mvnHome}/bin/mvn -f dme3-pkg/pom.xml clean install -DskipTests=true"
   
}
