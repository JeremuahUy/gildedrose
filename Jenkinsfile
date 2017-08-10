node {
   stage('preparation'){
       
       git credentialsId: 'a4c6b258-a143-4f62-83a7-29912551826e', url: 'https://github.com/JeremuahUy/gildedrose.git'
   }
   
   stage('build'){
       sh 'docker run -i --rm --name my-maven-project -v "$PWD":/usr/src/mymaven -w /usr/src/mymaven maven:3-jdk-8 mvn install'
       
   }
   
   stage('result'){
       
       junit '**/target/surefire-reports/TEST-*.xml'
       archiveArtifacts 'target/gildedrose-*.jar'
   }
}
