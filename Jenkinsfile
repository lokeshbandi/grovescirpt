#!/usr/bin/env groovy
pipeline {
    agent any
    stages {
        stage('stage one') {
            steps {
                script {
                    tags_extra = "value_1"
                }
                echo "git repo: ${GIT_REPO}"
                echo "git branch: ${GIT_BRANCH}"
                echo "tags_extra: ${tags_extra}"
            }
        }
        stage('stage two') {
            steps {
                echo "tags_extra: ${tags_extra}"
            }
        }
        stage('stage three') {
            when {
                expression { tags_extra != 'bla' }
            }
            steps {
                echo "tags_extra: ${tags_extra}"
            }
        }
    }
}