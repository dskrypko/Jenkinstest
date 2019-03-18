pipeline {

    parameters {
        string(name: 'IMG_REGISTRY', defaultValue: 'infobloxcto')
    }

    agent {
        label 'cdnsfw_dockerhub_ami'
    }

    stages {
        stage('Publishing new images') {
            steps {
                script {
                    def IMAGE_NAMES_LIST = sh (
                    script: '''
                        echo "onprem.agent"
                    ''',
                    returnStdout: true
                    ).trim().split(" ")

                    def IMAGE_VERSION = sh (
                        script: '''
                            echo "v2.0.0"
                        ''',
                        returnStdout: true
                    ).trim().split(" ")

                    imgLen = IMAGE_NAMES_LIST.length;
                    for (i = 0; i < imgLen; i++) {
                        def TMP_IMG="${env.IMG_REGISTRY}/${IMAGE_NAMES_LIST[i]}"
                        echo TMP_IMG
                    }
                }
            }
        }
    }
}
