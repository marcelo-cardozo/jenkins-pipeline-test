#!/usr/bin/env groovy
pipeline {
    agent any

    stages {
        GIT_BRANCH = sh(returnStdout: true, script: 'git rev-parse --abbrev-ref HEAD').trim()
        stage('Build') {
            stage('prod'){
                when {
                    expression {
                        GIT_BRANCH == 'master'
                    }
                }
                steps {
                    echo 'Building Prod..'
                }
            }
            stage('dev'){
                when {
                    expression {
                        GIT_BRANCH == 'develop'
                    }
                }
                steps {
                    echo 'Building Dev..'
                }
            }
        }
        stage('Test') {
            stage('prod'){
                when {
                    expression {
                        GIT_BRANCH == 'master'
                    }
                }
                steps {
                    echo 'Testing Prod..'
                }
            }
            stage('dev'){
                when {
                    expression {
                        GIT_BRANCH == 'develop'
                    }
                }
                steps {
                    echo 'Testing Dev..'
                }
            }
        }
        stage('Deploy') {
            stage('prod'){
                when {
                    expression {
                        GIT_BRANCH == 'master'
                    }
                }
                steps {
                    echo 'Deploying Prod..'
                }
            }
            stage('dev'){
                when {
                    expression {
                        GIT_BRANCH == 'develop'
                    }
                }
                steps {
                    echo 'Deploying Dev..'
                }
            }
        }
    }
}