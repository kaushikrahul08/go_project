node() {
    stage('checkout'){
        checkout scm
    }
    
    stage('azsplogin') {
     withCredentials([azureServicePrincipal('AKS-SP-ID')]) {
   //sh "az login --service-principal -u $AZURE_CLIENT_ID -p $AZURE_CLIENT_SECRET -t $AZURE_TENANT_ID"
  // sh "az acr login -n aksregus -u aksregus -p <password>"
                    }
    }
    
     stage('docker build&push'){
      sh "docker build -t webapp:latest ."
      sh "docker tag webapp:latest kaushikrahul08/webapp:latest"
      sh "docker login -u 'kaushikrahul08' -p 'Dristi@1381' docker.io"
      sh "docker push kaushikrahul08/webapp:latest"
    } 
    
}
