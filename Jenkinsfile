
basicPipeline {
    name = 'nmp'
    env = [
        'dev':['project':'csnr-devops-lab-deploy'],
        'test':['project':'csnr-devops-lab-deploy'],
        'prod':['project':'csnr-devops-lab-deploy', 'host':'nmp-csnr-devops-lab-deploy.pathfinder.gov.bc.ca']
    ]
    templates = [
        'build':[
            ['file':'OpenShift/dotnet-20.bc.json'],
            ['file':'OpenShift/dotnet-20-node.bc.json'],
            ['file':'OpenShift/nmp.bc.json'],
        ],
        'deployment':[
            ['file':'OpenShift/nmp.dc.json', 'params':['HOST':'${env[DEPLOY_ENV_NAME]?.host?:""}']]
        ]
    ]
}

