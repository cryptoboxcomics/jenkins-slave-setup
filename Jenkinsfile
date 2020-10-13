pipeline {
    agent any
    stages {
        stage("Lint role using molecule") {
            steps {
                sh """
                    python3 -m molecule lint
                """
            } //steps
        } //stage
        stage("Deploy role in test Docker containers") {
            steps {
                sh """
                    python3 -m molecule converge
                """
            } //steps
        } //stage
        stage("Destroy test Docker container") {
            steps {
                sh """
                    python3 -m molecule destroy
                """
            } //steps
        } //stage
    } //stages
} //pipeline