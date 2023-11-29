
node {

  
   def IMAGE="srv-web-enora"
	
    stage('Clone') {
          checkout scm
    }

    stage('Build') {
          docker.build("$IMAGE",  '.')
    }

    stage('Run image') {
        docker.image('srv-web-enora').withRun('-p 8054:80 --name srv_web-enora' ) { c ->

        sh 'docker ps | grep srv_web-enora'
	}

    }
}
