# terraform_gh_action

`This repo holds the terraform files needed to provision an EKS cluster to AWS via GitHub Actions on Pull Request.  It uses the EKS module/K8s provider and a Terraform Cloud account (trial version).`

`The GitHub Action performs terraform fmt, init, validate, etc.. if all steps succeded then connects to Terraform Cloud runs the plan waits for approval and applies the configuration. `

`Also for Terraform Cloud to authenticate against GitHub a token is needed. I created that manually in Terraform Cloud and set it in Github.` 

`missing TF files to complete this task:`

`IAM permissions listed on the EKS module documentation.`
`AWS IAM Authenticator`
 `manual steps`
`It takes aprox 10 mins for the cluster to be provisioned.`


`run below command to access the cluster via kubectl`

`aws eks --region $(terraform output -raw region) update-kubeconfig --name $(terraform output -raw cluster_name)`