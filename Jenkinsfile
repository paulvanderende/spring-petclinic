
stage('Build') {
    node('swarm') {
        checkout scm
        try {
            sh "./mvnw package"
        } catch (e) {
            throw e
        } finally {
            junit "**/TEST*.xml"
        }
    }

}
