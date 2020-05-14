node('master') 
{
    stage('Continuous Download') 
	{
    git 'https://github.com/ksnithya/jenkins_multibranch.git'
	}
    stage('Continuous Build') 
	{
    sh label: '', script: '/opt/maven/bin/mvn clean install package'
	}
    stage('Continuous Deployment') 
	{
    sh label: '', script: 'cp  /var/lib/jenkins/workspace/Scripted-Pipeline/webapp/target/webapp.war  /opt/tomcat/webapps/qaenv.war'
	}
    stage('Continuous Testing') 
	{
              sh label: '', script: 'echo "Testing Passed"'
	}
    stage('Continuous Delivery') 
	{
    sh label: '', script: 'scp  /var/lib/jenkins/workspace/Scripted-Pipeline/webapp/target/webapp.war jenkinadm@172.31.32.180:/opt/tomcat/webapps/prodenv.war'
	}
}
