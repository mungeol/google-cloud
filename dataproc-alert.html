Monitoring, Alerting 2 Slack
EDIT NOTIFICATION CHANNELS
Slack > ADD NEW > ALLOW
Slack Channel Name > Cloud Alerting Display Name > SEND TEST NOTIFICATION
If a private channel is specified, Invite Google Cloud Monitoring to the channel
Save
Up to Alerting overview page
CREATE POLICY > SELECT A METRIC
Cloud Dataproc Cluster > N metrics > Cluster > N metrics > Failed jobs > Apply
ADD FILTER > error_type = DATAPROC_SERVER_ERROR > DONE
Rolling window function, delta > NEXT
Threshold value, 0 > NEXT
Notification Channels > Slack, the channel name > OK
Alert policy name > NEXT
CREATE POLICY

Eventarc, Workflows 2 Slack
Eventarc, google.cloud.dataproc.v1.ClusterController.DeleteCluster triggers a Workflow
Workflows, check job status > send a slack message if it equals ERROR
Sample
main:
    params: [input]
    steps:
    - assignArgs:
            assign:
            - projectID: ${sys.get_env("GOOGLE_CLOUD_PROJECT_ID")}
            - response: ${input}
            - jobId: ${"step-spark-postgresql-2-bigquery-" + text.substring(response.data.resource.labels.cluster_name, 36, 49)}
    - checkOperation:
            switch:
                - condition: ${"first" in response.data.operation}
                  next: getJob
            next: returnOutput
    - getJob:
            call: http.get
            args:
                auth:
                    type: OAuth2
                    scopes: https://www.googleapis.com/auth/cloud-platform
                url: ${"https://dataproc.googleapis.com/v1/projects/" + projectID + "/regions/asia-northeast1/jobs/" + jobId}
            result: response
    - checkStatus:
            switch:
                - condition: ${response.body.status.state == "ERROR"}
                  next: sendSlack
            next: returnOutput
    - sendSlack:
            call: http.post
            args:
                headers: {Content-type: application/json, Authorization: Bearer xoxb-your-token}
                url: https://slack.com/api/chat.postMessage
                body: { "channel": "C04CTKH1JBZ", "text": '${"https://console.cloud.google.com/dataproc/jobs/" + jobId + "?region=asia-northeast1&project=" + projectID}'}
    - returnOutput:
            return: ${response}
