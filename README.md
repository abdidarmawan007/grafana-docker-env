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

### domain
        - name: GF_SERVER_ROOT_URL
          value: https://grafana-101.abdidarmawan.com
