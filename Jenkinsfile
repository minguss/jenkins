pipeline {
    agent any

    parameters {
        string(name: 'Version', defaultValue: 'lastest', description: 'Version정보를 입력하세요.')
        choice(name: 'CHOICE', choices: ['Dev', 'Prod'], description: '배포 대상을 선택하세요.')
    }

    stages {
        stage('Dev') {
            when {
                expression { ${params.CHOICE} == 'Dev' }
            }
            steps {
                echo "Hello ${params.CHOICE}"
                echo "Hello ${params.Version}"
            }
        }
        stage('Prod') {
            when {
                expression { ${params.CHOICE} == 'Prod' }
            }
            steps {
                echo "Hello ${params.CHOICE}"
                echo "Hello ${params.Version}"
            }
        }
    }
}
	
