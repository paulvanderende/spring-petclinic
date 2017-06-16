
stage('Build') {
    node('swarm') {
        checkout scm
        try {
            sh "./mvnw clean build package"
        } catch (e) {
            throw e
        } finally {
            junit "**/TEST*.xml"
        }
    }

}
