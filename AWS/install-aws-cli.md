## How to install AWS Cli?

Docs: https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html

MSI:
msiexec.exe /i https://awscli.amazonaws.com/AWSCLIV2.msi /qn


- To confirm the installation, open the Start menu, search for cmd to open a command prompt window, and at the command prompt use the aws --version command.


C:\> aws --version
aws-cli/2.25.11 Python/3.11.6 Windows/10 exe/AMD64 prompt/off

- If Windows is unable to find the program, you might need to close and reopen the command prompt window to refresh the path, or follow the troubleshooting in Troubleshooting errors for the AWS CLI.