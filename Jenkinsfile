pipeline {
		agent {
		label "master"
		}
		
		parameters {
			string(defaultValue: "https://github.com/shambhukr/sample-pipeline.git", description: 'RepoUrl', name: 'RepoUrl')
			string(defaultValue: "sample-seed-job", description: 'ProjectName', name: 'ProjectName')
       
		}
		
		stages {
			stage ('Generate seed job') {
				steps {
				    

jobDsl scriptText: '''def scmRepo = RepoUrl
def seedJob = ProjectName
multibranchPipelineJob(seedJob) {
		branchSources {
			git {
				remote(scmRepo)
				credentialsId(\'\')
				includes(\'*\')
			}
		}
		orphanedItemStrategy {
			discardOldItems {
				numToKeep(20)
			}
		}
}'''



					
				}
			}
		}	
	}
	
