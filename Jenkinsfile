pipeline {
    agent none
    stages {
        stage('Build') {
            steps {
                script {
                    // Define Docker image to use
                    def dockerImage = 'openjdk:11'

                    // Checkout source code from Git repository
                    git 'https://github.com/your/repository.git'

                    // Run pipeline inside a Docker container
                    docker.image(dockerImage).inside('-v $HOME/.m2:/root/.m2') {
                        // Compile Java code
                        sh 'mvn clean package'

                        // Run the Java program
                        sh 'java -cp target/classes com.example.Main'
                    }
                }
            }
        }
    }
}

