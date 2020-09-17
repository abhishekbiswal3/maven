node {
    try{
       emailext body: '', subject: 'started jobs !!!!!', to: 'biswal.avishek@gmail.com'
       stage 'checkout'
       git 'https://github.com/abhishekbiswal3/maven'
       stage 'compile'
       bat label: '', script: 'mvn clean package'
       stage 'archive artifacts'
       step([$class: 'JUnitResultArchiver', allowEmptyResults: true, testResults: '/target/test-*.xml'])
       archiveArtifacts 'target/*.war'
       }
    

        catch (all){
          notify("caught: ${all}")
          currentBuild.result = 'Failure'
        }
        
}
