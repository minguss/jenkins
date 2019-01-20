pipeline {
	  def label = "sumapp-${UUID.randomUUID().toString()}"
		podTemplate(label: label, 
		containers: [
			containerTemplate(name: 'kubectl', image: 'lachlanevenson/k8s-kubectl:v1.8.0', command: 'cat', ttyEnabled: true)
		],
		volumes: [hostPathVolume(hostPath: '/var/run/docker.sock', mountPath: '/var/run/docker.sock')]
		) {
	node(label) {

    parameters {
        string(name: 'Version', defaultValue: 'lastest', description: 'Version정보를 입력하세요.')
        choice(name: 'CHOICE', choices: ['Dev', 'Prod'], description: '배포 대상을 선택하세요.')
    }

    stages {
        stage('Dev') {
            when {
                expression { params.CHOICE == 'Dev' }
            }
            steps {
                echo "Hello ${params.CHOICE}"
                echo "Hello ${params.Version}"
		sh "kubectl get psp"
            }
        }
        stage('Prod') {
            when {
                expression { params.CHOICE == 'Prod' }
            }
            steps {
                echo "Hello ${params.CHOICE}"
                echo "Hello ${params.Version}"
            }
        }
    }
		}
}
}
	
