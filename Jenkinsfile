@Library('piper-lib-os') _

node() {
  stage('init') {
    deleteDir()
    checkout scm
    setupCommonPipelineEnvironment script: this
  }
  stage('deployIntegrationArtifact Command') {
     integrationArtifactDeploy script: this
  }
  stage('integrationArtifactGetServiceEndpoint Command') {
    print "Service Endpoint:"
		integrationArtifactGetServiceEndpoint script: this
    print  commonPipelineEnvironment.getValue("integrationFlowServiceEndpoint")
  }
}
