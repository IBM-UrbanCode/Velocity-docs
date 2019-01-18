node ('ip-10-134-116-65.ec2.internal') {

   // Mark the code checkout 'stage'....
   stage ('Checkout') {
      // Checkout code from repository
      checkout scm
      dir('theme') {
          checkout([
            $class: 'GitSCM',
            branches: [[name: 'master']],
            doGenerateSubmoduleConfigurations: false,
            extensions: [],
            submoduleCfg: [],
            userRemoteConfigs: [[url: 'https://github.com/IBM-UrbanCode/mkdocs-windmill']]
          ])
      }
   }

    // Mark the code build 'stage'....
    stage ('Build') {
        environment {
            WINDMILL_DIR = 'theme/mkdocs-windmill'
        }
        bat "set WINDMILL_DIR=theme/mkdocs-windmill"
        bat "type mkdocs.yml"
        bat "dir"
        bat "dir theme"
        bat "dir theme/mkdocs-windmill"
        bat "echo %WINDMILL_DIR%"
        bat "mkdocs build"
    }

  // Mark the code save 'stage'....
   stage ('Save') {
      bat "cd site/"
      bat "dir"
      bat "dir site"
      archiveArtifacts artifacts: 'site/**/*', fingerprint: true
   }

    // Mark the code upload 'stage'....
    stage ('Upload') {
       step([$class: 'UCDeployPublisher',
            siteName: 'UrbanCode Production',
            component: [
                $class: 'com.urbancode.jenkins.plugins.ucdeploy.VersionHelper$VersionBlock',
                componentName: 'HCL Velocity ${BRANCH_NAME} Docs',
                createComponent: [
                    $class: 'com.urbancode.jenkins.plugins.ucdeploy.ComponentHelper$CreateComponentBlock',
                    componentTemplate: 'HCL Documentation Template',
                    componentApplication: 'HCL Documentation'
                ],
                delivery: [
                    $class: 'com.urbancode.jenkins.plugins.ucdeploy.DeliveryHelper$Push',
                    pushVersion: '${BRANCH_NAME}_${BUILD_NUMBER}',
                    baseDir: pwd() + '/site',
                    fileIncludePatterns: '**/*',
                    fileExcludePatterns: '',
                    pushProperties: 'product=velocity\nproduct.version=${BRANCH_NAME}\nbuild.number=${BUILD_NUMBER}',
                    pushDescription: 'Pushed from Jenkins'
                ]
            ]
        ])
    }
}
