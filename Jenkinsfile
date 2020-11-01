#!/usr/bin/env groovy
pipeline {
    agent any

    stages {
        stage('Build') {
            parallel {
                stage('prod') {
                    when { branch 'master' }
                    steps {
                        echo 'Building Prod..'
                    }
                }
                stage('dev') {
                    when { branch 'develop' }
                    steps {
                        echo 'Building Dev..'
                    }
                }
            }
        }
        stage('Test') {
            parallel {
                stage('prod') {
                    when { branch 'master' }
                    steps {
                        echo 'Testing Prod..'
                    }
                }
                stage('dev') {
                    when { branch 'develop' }
                    steps {
                        echo 'Testing Dev..'
                    }
                }
            }
        }
        stage('Deploy') {
            parallel {
                stage('prod') {
                    when { branch 'master' }
                    steps {
                        echo 'Deploying Prod..'
                    }
                }
                stage('dev') {
                    when { branch 'develop' }
                    steps {
                        echo 'Deploying Dev..'
                    }
                }
            }
        }
    }
}