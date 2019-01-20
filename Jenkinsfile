pipeline {
    agent any

    parameters {
        myStage = string(name: 'Version', defaultValue: 'lastest', description: 'Version정보를 입력하세요.')
        myVersion = choice(name: 'CHOICE', choices: ['Dev', 'Prod'], description: '배포 대상을 선택하세요.')
    }

    stages {
        stage('Dev') {
            when {
                expression { myStage == 'Dev' }
            }
            steps {
                echo "Hello ${params.myStage}"
                echo "Hello ${params.myVersion}"
            }
        }
        stage('Prod') {
            when {
                expression { myStage == 'Prod' }
            }
            steps {
                echo "Hello ${params.myStage}"
                echo "Hello ${params.myVersion}"
            }
        }
    }
}
	
