pipeline { 
    agent any 
    stages {
        stage('Git-CheckOut') { 
            steps { 
                //sh 'make'
                echo "checking out from git repo"
                git 'https://github.com/cchen1988/jenkins_pipeline.git'
            }
        }
        stage('Build'){
            steps {
                //sh 'make check'
                //junit 'reports/**/*.xml'
                echo "Building the checkout-out project"
                sh "python3 build.py"
            }
        }
        stage('UnitTest'){
            steps {
                //sh 'make check'
                //junit 'reports/**/*.xml'
                echo "run unit test"
                sh "python3 unit_test.py"
            }
        }
        stage('Deploy') {
            steps {
                //sh 'make publish'
                echo "Deployed successfully"
                sh "python3 deploy.py"
            }
        }
    }
}
