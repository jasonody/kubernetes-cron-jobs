# kubernetes-cron-jobs

Playing with kubernetes cron jobs

[Source](https://kubernetes.io/docs/tasks/job/automated-tasks-with-cron-jobs/)

Create cron job: `kubectl create -f ./jobs/hello-world-cron-job.yaml`

Get cron jobs: `kubectl get cronjobs`
Watch jobs: `kubectl get jobs --watch`
Get the logs from one of the pods for this job: `kubectl logs $(kubectl get pods -o wide | grep hello-world-cron-job | head -n 1 | awk '{print $1}')`

Delete cron job: `kubectl delete cronjob hello-world-cron-jobs` or `kubectl delete -f ./jobs/hello-world-cron-job.yaml`