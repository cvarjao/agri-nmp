#!groovy

def bcModels(){
    def models = []
        models.add(['-f', 'OpenShift/dotnet-20.bc.json',
         '-p', 'NAME_SUFFIX=${buildNameSuffix}'])

        models.add(['-f', 'OpenShift/dotnet-20-node.bc.json',
         '-p', 'NAME_SUFFIX=${buildNameSuffix}',
         '-p', 'SOURCE_REPOSITORY_URL=${gitRepoUrl}'])

        models.add(['-f', 'OpenShift/nmp.bc.json',
         '-p', 'NAME_SUFFIX=${buildNameSuffix}',
         '-p', 'SOURCE_REPOSITORY_URL=${gitRepoUrl}'])
    return models;
}

def dcModels(){
    def models = []

    models.add(['-f', 'OpenShift/nmp.dc.json',
     '-p', 'NAME_SUFFIX=${dcSuffix}',
     '-p', 'ENV_NAME=${envName}'])

    return models;
}


basicPipeline {
    name = 'nmp'
    env = [
        'dev':['project':'csnr-devops-lab-deploy'],
        'test':['project':'csnr-devops-lab-deploy'],
        'prod':['project':'csnr-devops-lab-deploy']
    ]
    templates = [
        ['file':'OpenShift/dotnet-20.bc.json'],
        ['file':'OpenShift/dotnet-20-node.bc.json'],
        ['file':'OpenShift/nmp.bc.json'],
        ['file':'OpenShift/nmp.dc.json']
    ]
    bcModels = bcModels()
    dcModels = dcModels()
}
