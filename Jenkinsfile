node ('ip-10-134-116-65.ec2.internal') {

   // Mark the code checkout 'stage'....
   stage ('Checkout') {
      // Checkout code from repository
      checkout scm
      checkout([
        $class: 'GitSCM',
        branches: [[name: 'master']],
        doGenerateSubmoduleConfigurations: false,
        extensions: [],
        submoduleCfg: [],
        userRemoteConfigs: [[url: 'https://github.com/IBM-UrbanCode/mkdocs-windmill']]
      ])
   }

   // Mark the code build 'stage'....
   stage ('Build') {
      bat "set WINDMILL_DIR=mkdocs-windmill/mkdocs-windmill"
      bat "mkdocs build"
   }

  // Mark the code save 'stage'....
   stage ('Save') {
      bat "mv site/"
      archiveArtifacts artfacts: '**/*', fingerprint: true
   }

    // Mark the code upload 'stage'....
    stage ('Upload') {
        bat "echo ls"
    }
}
