pipeline {
    agent// any
stages {
    stage('Check Out code from git'){
        steps{
        git branch: 'master', url: "https://github.com/Timi-0/nodeapp.git"
            }
    }
           
    stage ('Artifactory configuration') {
        steps {
            
            rtNpmResolver (
                id: "NPM_RESOLVER",
                serverId: "MYARTIFACTORY",
                repo: "npm-remote"
            )

            rtNpmDeployer (
                id: "NPM_DEPLOYER",
                serverId: "MYARTIFACTORY",
                repo: "npm-local"
            )
            
rtNpmInstall (
    // Optional tool name from Jenkins configuration
 //   tool: NPM_TOOL,
    // Optional path to the project root. If not set, the root of the workspace is assumed as the root project path.
    path: '.',
    // Optional npm flags or arguments.
 //   args: '--verbose',
    resolverId: 'NPM_RESOLVER'
 
)
    }
            }        
    stage('check npm version and setup'){
        steps{
        sh 'npm --version'
            sh 'ls -altr'
            sh 'npm config list'
        }
}

        
}
    
    
}
