# Usage

You may need the utilities from the `utils` directory to work with **pboted**.   
In the future, their list will grow.   
There are plans to transfer all means for interaction into a separate CLI utility.

You can only continue to use your Java I2P-Bote identities if:

- your address is created using the ECDH-256/ECDSA-256/AES-256/SHA-256 algorithm (others are not supported yet)
- identities file is not encrypted (encrypted files are not supported yet)

## Sending email

### SMTP

To be able to send email through SMTP you need to:

- Fill `[smtp]` section in configuration file with [parameters](configuration.md)
- Restart the **pboted** to apply the settings
- After loading, you be able to connect to the specified SMTP port manually or with your mail client

### Via `outbox` directory 

- Prepare plain test message
- Format it with `message_formatter`
- Put result file to `outbox` directory in pboted working directory
- pboted will automatically check `outbox` and send email
- After sending email file will be moved to `sent` directory

## Receiving email

After starting with a generated identity the application will begin its normal job of searching for mail.  
If mail for identity are found, they will be placed in the `inbox` directory.

### POP3

To be able to receive email through POP3 you need to:

- Fill [pop3] section in configuration file with [parameters](configuration.md)
- Restart the **pboted** to apply the settings
- After loading, you be able to connect to the specified POP3 port manually or with your mail client.