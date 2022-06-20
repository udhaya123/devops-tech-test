# DevOps Engineer - technical interview

## Testing goals
- With this test, we want to see your ability to create an entire infrastructure from scratch as well as your skills as a system administrator.

## The task
- Your task is to provision a highly available CMS with a MySQL RDS backend and nginx/httpd frontend proxy. The entry point of the cluster should be a host and port 443.

## The solution

- In your solution, please emphasise on readability, maintainability and DevOps methodologies. We expect a clear way to recreate your setup.
- Since you have to have an HA config using 443 please use a self-signed cert.
- Use an infrastructure as code tool of choice (Terraform, Ansible, chef) as the configuration management tool.
- The infrastructure provider should be AWS.
- It should run on Centos7, using security best practices.
- Make sure to include a README.md with clear instructions, so we can run your code.
- A clean bare minimum working infrastructure is preferred than a full-blown solution pieced together with scissors, rope and duct tape. Do not skip security considerations.

## When you are finished
- Submit your solution to a Github repository and send us a link.
- Make sure your README tells us how to run it.
- Please fork this repo so that you are tested against the test that you started with, as this test may change.

## Bonus points
- If you can document all aspects of your code, in the README and within the code itself.
- If you can generate the self-signed cert/key.