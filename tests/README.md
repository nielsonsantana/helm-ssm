## Functional example with codacy/helm-ssm

helm installation

	curl https://get.helm.sh/helm-v3.2.0-linux-amd64.tar.gz --output helm-linux-amd64.tar.gz
	tar xvf helm-linux-amd64.tar.gz
	rm helm-linux-amd64.tar.gz

Install SSM plugin

	helm plugin install https://github.com/codacy/helm-ssm/releases/download/latest/helm-ssm-linux.tgz

Set AWS Configs

	export AWS_ACCESS_KEY_ID= your access id
	export AWS_SECRET_ACCESS_KEY=your secret key

Test using 

	helm ssm -v -d -f tests/testchart/values.yaml > develop/values.yaml
	helm install testchart --values develop/values.yaml --debug --dry-run --generate-name