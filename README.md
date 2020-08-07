# kubernetes-cron-jobs

Playing with kubernetes cron jobs

[Source](https://kubernetes.io/docs/tasks/job/automated-tasks-with-cron-jobs/)

## Hello world cron job

Create cron job: `kubectl create -f ./jobs/hello-world-cron-job.yaml`

Get cron jobs: `kubectl get cronjobs`

Watch jobs: `kubectl get jobs --watch`

Get the logs from one of the pods for this job: `kubectl logs $(kubectl get pods -o wide | grep hello-world-cron-job | head -n 1 | awk '{print $1}')`

Delete cron job: `kubectl delete cronjob hello-world-cron-jobs` or `kubectl delete -f ./jobs/hello-world-cron-job.yaml`

----

Play with kubernetes jobs

[Source](https://medium.com/better-programming/tutorial-how-to-use-kubernetes-job-and-cronjob-1ef4ffbc8e84)

## Enforcing a time limit

Create cron job: `kubectl create -f ./jobs/enforcing-a-time-limit.yaml`

Check that the deadline was enforced: `kubectl get job enforcing-a-time-limit -o yaml` or `kubectl describe job enforcing-a-time-limit` (check for "DeadlineExceeded")

Delete job: `kubectl delete job enforcing-a-time-limit` or `kubectl delete -f ./jobs/enforcing-a-time-limit.yaml`
