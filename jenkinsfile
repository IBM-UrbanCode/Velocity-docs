node ('ip-10-134-116-65.ec2.internal') {
   // Mark the code checkout 'stage'....
   stage ('Checkout') {
      // Checkout code from repository
      checkout scm
   }

   // Mark the code build 'stage'....
   stage ('Build') {
      sh "mkdocs build"
   }

  // Mark the code save 'stage'....
   stage ('Save)' {
      sh "mv site/"
      archiveArtifacts artfacts: '**/*', fingerprint: true
   }

    // Mark the code upload 'stage'....
    stage ('Upload') {

    }
}
