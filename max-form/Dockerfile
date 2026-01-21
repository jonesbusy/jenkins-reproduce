FROM jenkins/jenkins:2.546-jdk21

ADD plugins.txt /var/jenkins_home/plugins.txt
RUN jenkins-plugin-cli --plugin-file /var/jenkins_home/plugins.txt --verbose --latest true --view-security-warnings --output txt

ENV JAVA_TOOL_OPTIONS "-Djenkins.install.runSetupWizard=false -Djava.awt.headless=true -Dcasc.merge.strategy=override"

ENV CASC_RELOAD_TOKEN=local

ENV CASC_JENKINS_CONFIG "/var/casc_configs/jcasc.yaml"
COPY jcasc.yaml /var/casc_configs/jcasc.yaml
