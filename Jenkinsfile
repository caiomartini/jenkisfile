#!/usr/bin/env groovy

node {
    stage("Checkout") {
        deleteDir()
        checkout scm
    }
    stage("Build") {
		bat "\"${tool 'MSBuild'}\" ConsoleApp1/ConsoleApp1.sln /p:Configuration=Release /p:Platform=\"Any CPU\" /p:ProductVersion=1.0.0.${env.BUILD_NUMBER}"
    }
}