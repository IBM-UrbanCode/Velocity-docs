node ('ip-10-134-116-65.ec2.internal') {

   // Mark the code checkout 'stage'....
   stage ('Checkout') {
      // Checkout Documentation code from repository
      checkout scm

      // Checkout UrbanCode Windmill Theme
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
      // Relative directory where the theme is downloaded
      env.WINDMILL_DIR = 'theme/mkdocs_windmill'

      env.DOC_VERSION = "${BRANCH_NAME}_${BUILD_NUMBER}"
      env.DOC_VERSIONN = env.DOC_VERSION
      env.DOC_VERSIONNN = '%BRANCH_NAME%_%BUILD_NUMBER%'
      // env.DOC_VERSIONNNN = %BRANCH_NAME% %BUILD_NUMBER%
      env.DOC_VERSIONNNNN = "${env.BRANCH_NAME}_${env.BUILD_NUMBER}"
      bat "set"

      // Build documentation
      bat "mkdocs build"
   }

  // Mark the code save 'stage'....
   stage ('Save') {
      // Sanity check of site contents.
      bat "dir site"

      // Save documentation in Jenkins
      archiveArtifacts artifacts: 'site/**/*', fingerprint: true
   }

    // Mark the code upload 'stage'....
    stage ('Upload') {

    env.DOC_VERSION = '${BRANCH_NAME}_${BUILD_NUMBER}'

       // Add built documentation files as component version in UrbanCode Deploy
       step([$class: 'UCDeployPublisher',
            siteName: 'UrbanCode Production',
            // Specify Component
            component: [
                $class: 'com.urbancode.jenkins.plugins.ucdeploy.VersionHelper$VersionBlock',
                componentName: 'HCL Velocity ${BRANCH_NAME} Docs',
                // Create Component and add to Application if it doesn't exist
                createComponent: [
                    $class: 'com.urbancode.jenkins.plugins.ucdeploy.ComponentHelper$CreateComponentBlock',
                    componentTemplate: 'HCL Documentation Template',
                    componentApplication: 'HCL Documentation'
                ],
                // Add files to component verison
                delivery: [
                    $class: 'com.urbancode.jenkins.plugins.ucdeploy.DeliveryHelper$Push',
                    pushVersion: env.DOC_VERSION,
                    baseDir: pwd() + '/site',
                    fileIncludePatterns: '**/*',
                    fileExcludePatterns: '',
                    pushProperties: 'product=velocity\nproduct.version=${BRANCH_NAME}\nbuild.number=${BUILD_NUMBER}',
                    pushDescription: 'Pushed from Jenkins'
                ]
            ],
            // Deploy the built version to test instance
            deploy: [
                $class: 'com.urbancode.jenkins.plugins.ucdeploy.DeployHelper$DeployBlock',
                deployApp: 'HCL Documentation',
                deployEnv: 'Test (uc-doc-test)',
                deployProc: 'Upload Documentation',
                deployReqProps: '',
                deployVersions: 'HCL Velocity ${BRANCH_NAME} Docs:' + env.DOC_VERSION,
                deployOnlyChanged: false
            ]
        ])
    }
}
