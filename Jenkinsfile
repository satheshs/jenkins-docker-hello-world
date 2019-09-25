// The URL of the Docker registry images will be pushed into during the build process.
dockerRegistryUrl = "448091595882.dkr.ecr.us-east-2.amazonaws.com"

// The name of the Docker image we'll push.
dockerImageName= "apache"


// The name of the product. Assumed to be the name of the Git repo. Also used in creating the messages for sending to the Slack channel.
productName = "edw2.0"

config = [
    "master": [
        "vmUserName": "buyinnovroot",
        "vmIpAddress": "10.246.1.17",
    ]
    ]


def getBranchParentDir() {
    rawBranch = env.BRANCH_NAME
    echo rawBranch

    startIndex = rawBranch.indexOf('/')

    if (startIndex == -1) {
        return rawBranch
    }

    return rawBranch.substring(0, startIndex)
}

def getConfigValue(name) {
    configHash = config[getBranchParentDir()]
    if (configHash == null) {
        return ""
    }
    return configHash[name]
}

def getComputedImageFullName() {
    rawVersion = getVersionFromGitCommit()
    return "${dockerRegistryUrl}/${dockerImageName}:${rawVersion}"
}

def getVersionFromGitCommit() {
    git_commit = sh ( script: 'git describe --abbrev=0 --tags',
    returnStdout: true
    ).trim()
    echo "The tag is ....... $git_commit"
    return "$git_commit"
}


pipeline {
    agent any
        environment {
        GIT_URL = 'https://github.com/satheshs/jenkins-docker-hello-world.git'
        }
    stages {
        stage('checkout') {
            steps {
                deleteDir()
                git credentialsId: 'b728e187-9a27-4afd-9aa9-8736634134b4', url: "${GIT_URL}"
            }
        }
        stage('Build the image') {
            steps {
                echo "Build step"
                sh "docker build -t ${getComputedImageFullName()} -f Dockerfile ."
            }
        }
    }
}
