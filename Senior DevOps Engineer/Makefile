SHELL=/bin/bash -euxo pipefail

ENV_FILE ?= config.json
Parameters = $(shell jq -c '.Parameters | to_entries | map(select(.value != "")) | .[] | "\(.key)=\(.value)"' $(ENV_FILE))

iam-sg:
	aws cloudformation deploy \
		--template-file  ./template/roles_securityGroups.yaml \
		--stack-name iam-securityGroup-Stack \
		--capabilities CAPABILITY_IAM \
		--parameter-overrides $(Parameters)

createCluster:
	aws cloudformation deploy \
		--template-file  ./template/cluster.yaml \
		--stack-name eksCluster-Stack \
		--capabilities CAPABILITY_IAM \
		--parameter-overrides $(Parameters)

applyConfigMap:
	kubectl apply -f kubernetes/aws-auth-cm.yml

CreateNodeGroup:
	aws cloudformation deploy \
		--template-file  ./template/nodeGroup.yaml \
		--stack-name eksNodegroup \
		--capabilities CAPABILITY_IAM \
		--parameter-overrides $(Parameters)

deploy:
	kubectl apply -f kubernetes/deployment.yaml