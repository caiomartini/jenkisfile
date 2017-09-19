#!/usr/bin/env groovy

import groovy.io.FileType

node {
    stage("Checkout") {
        deleteDir()
        checkout scm
    }
    stage("Build") {
        def list = []
        def dir = new File("path_to_parent_dir")
        dir.eachFileRecurse (FileType.FILES) { file ->
            list << file
        }
        list.each {
            println it.path
            bat "\"${tool 'MSBuild'}\" ConsoleApp1/${params.Solution}.sln /m /p:Configuration=Release /p:Platform=\"Any CPU\" /p:ProductVersion=1.0.0.${env.BUILD_NUMBER}"
            archiveArtifacts "**/bin/Release/*.*"
        }        
    }
}