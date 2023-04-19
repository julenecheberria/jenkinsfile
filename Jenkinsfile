pipeline {
  agent any
  stages {
    stage('Checkout Scm') {
      steps {
        git 'https://github.com/julenecheberria/apinetcurso.git'
      }
    }

    stage('dependencias') {
      steps {
        bat 'c:\\users\\puntonet\\tools\\nuget.exe restore -DirectDownload  -SolutionDirectory . apinetcurso.sln'
      }
    }

    stage('build') {
      steps {
       
	bat '"C:\\Program Files (x86)\\Microsoft Visual Studio\\2017\\Community\\MSBuild\\15.0\\Bin\\MSBuild.exe" apinetcurso.sln'
      }
    }

   
    stage('test') {
      steps {
        
	bat '"C:\\Program Files (x86)\\Microsoft Visual Studio\\2017\\Community\\Common7\\IDE\\CommonExtensions\\Microsoft\\TestWindow\\vstest.console.exe" apitest\bin\Debug\apitest.dll'
      }
    }

  }
}