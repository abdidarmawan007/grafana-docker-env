### credential and port
      - env:- env:
        - name: GRAFANA_PORT
          value: "3000"
        - name: GF_SECURITY_ADMIN_USER
          valueFrom:
            secretKeyRef:
              key: username
              name: grafana_101
        - name: GF_SECURITY_ADMIN_PASSWORD
          valueFrom:
            secretKeyRef:
              key: passphrase
              name: grafana_101
        - name: GF_AUTH_BASIC_ENABLED
          value: "true"
        - name: GF_AUTH_ANONYMOUS_ENABLED
          value: "false"
        - name: GF_AUTH_DISABLE_LOGIN_FORM
          value: "false"
### persistent storage
        - name: GF_PATHS_DATA
          value: /data/grafana
### domain
        - name: GF_SERVER_ROOT_URL
          value: https://grafana-101.abdidarmawan.com          
### aws key and region
        - name: GF_AWS_default_ACCESS_KEY_ID
          value: "xxxxxxx"
        - name: GF_AWS_default_SECRET_ACCESS_KEY
          value: "xxxxxxx"
        - name: GF_AWS_default_REGION
          value: "ap-southeast-1"
### aws s3 store images alert
        - name: GF_EXTERNAL_IMAGE_STORAGE_PROVIDER
          value: "s3"
        - name: GF_EXTERNAL_IMAGE_STORAGE_S3_BUCKET
          value: "my-aws-public-bucket"
        - name: GF_EXTERNAL_IMAGE_STORAGE_S3_REGION
          value: "ap-southeast-1"
        - name: GF_EXTERNAL_IMAGE_STORAGE_S3_ACCESS_KEY
          value: "xxxxx"
        - name: GF_EXTERNAL_IMAGE_STORAGE_S3_SECRET_KEY
          value: "xxxxx"
### gcp storage store images alert
        - name: GF_EXTERNAL_IMAGE_STORAGE_PROVIDER
          value: "gcs"
        - name: GF_EXTERNAL_IMAGE_STORAGE_GCS_KEY_FILE
          value: "/var/lib/grafana/service_account.json"
        - name: GF_EXTERNAL_IMAGE_STORAGE_GCS_BUCKET
          value: "my-gcp-public-bucket"
