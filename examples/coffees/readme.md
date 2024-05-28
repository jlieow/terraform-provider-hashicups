# Save all Terraform log output

Viewing log output inline with the running command is helpful if you plan on looking through the logs in the same terminal session or want to pipe the output to other shell commands, such as grep. Terraform can instead write this output to a log file on the local filesystem for opening in text editors or for archiving purposes.

Run a Terraform plan with both the TF_LOG and TF_LOG_PATH environment variables set.

$ TF_LOG=TRACE TF_LOG_PATH=trace.txt terraform plan