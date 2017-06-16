

def javaEnv() {
    def javaHome = tool "JDK"
    ["PATH=${env.PATH}:${javaHome}/bin", "JAVA_HOME=${javaHome}"]
}

stage('Build') {
    node('swarm') {
        checkout scm
        try {
            withEnv(javaEnv()) {
                sh "./mvnw package"
            }
        } catch (e) {
            throw e
        } finally {
            junit "**/TEST*.xml"
        }
    }

}
