pipeline{

    agent{
	label "master"
}

    stages {

        stage("build") {

            steps {
            echo "building the application"
            echo 'npm i'
            echo 'npm run build'
            echo "skipping build. Build already exists..."

            }

        }


        stage("deploying") {

            steps {
            echo "deploying the application using ansible-playbook"
	sh '''
	ansible-playbook -i inventory angular-app-deploy.yml --key-file /var/lib/jenkins/ansible
	'''

            }

        }

    }

}
