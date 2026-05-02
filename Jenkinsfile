pipline{
    agent any
    
    environment {
        VERCEL_TOKEN = credentials('vercel-token')
    }
    
    stages {
        stage("install dependencies") {
            steps {
                echo "Installing dependencies..."
                sh 'npm install'
            }
        }
        stage("Test") {
            steps {
                echo "Testing..."
                sh 'npm test'
            }
        }
          stage("Build") {
            steps {
                echo "Building..."
                sh 'npm run build'
            }
        }
          stage("Deploy") {
            steps {
                echo "Deploying..."
                sh 'npx vercel --prod --yes --token=%VERCEL_TOKEN%'
            }
        }
    }
}
