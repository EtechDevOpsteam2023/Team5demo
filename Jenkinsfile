pipeline{
	agent any 
	stages{
		stage('1-clone'){
			steps{
				checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'git-id', url: 'https://github.com/EtechDevOpsteam2023/Team5demo.git']])
			}
		}
		stage('2-systemchecks'){
			steps{
				sh 'sudo systemctl status jenkins'
			}
		}
		stage('3-diskcheck'){
			steps{
				sh 'df -h'
			}
		}
		stage('4-blockcheck'){
			steps{
				sh 'lsblk'
			}
		}
		stage('5-scriptcontrol'){
            steps{
                sh 'bash -x /var/lib/jenkins/workspace/Team5-job-demo/script.sh'
            }
        }
	}
}