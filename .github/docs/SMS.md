# Enable SMS Notifications from GitHub Actions

#### You can get SMS notifications sent from your GitHub Actions using the [Twilio SMS GitHub Action](https://github.com/twilio-labs/actions-sms)

### Prerequisites

- Twillio [Account (FREE)](https://www.twilio.com/try-twilio)
- Twillio [API Key & Secret](https://www.twilio.com/try-twilio)

### Usage

1. Set up your credentials in secrets in your repository and settings using the variable names `TWILIO_ACCOUNT_SID`, `TWILIO_API_KEY`, `TWILIO_API_SECRET`


2. Add the following to your workflows:

```yml
- name: 'Send SMS Notification'
  uses: twilio-labs/actions-sms@v1
  with:
    fromPhoneNumber: '+1(234)5678901'
    toPhoneNumber: '+1(234)3334444'
    message: 'Hello from Twilio'
  env:
    TWILIO_ACCOUNT_SID: ${{ secrets.TWILIO_ACCOUNT_SID }}
    TWILIO_API_KEY: ${{ secrets.TWILIO_API_KEY }}
    TWILIO_API_SECRET: ${{ secrets.TWILIO_API_SECRET }}
```

### INPUTS

`fromPhoneNumber`
`toPhoneNumber`
`message`
`TWILIO_ACCOUNT_SID`
`TWILIO_API_KEY`
`TWILIO_API_SECRET`

### OUTPUTS

`messageSid`