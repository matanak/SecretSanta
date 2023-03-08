# SecretSanta
This python-based script will automatically assign a recipient for every Secret Santa and send an email to each Secret Santa informing them of their recipient's name.

## Requirements

* Python
* SMTP server used to automatically send emails

## Instructions

### 1. Get The Script

git clone https:github.com/minamiaiko/secretsanta.git

### 2. Modify the Configuration File

Make your desired modifications to the config.py configuration file.

In it, you must specify:

* The SMTP settings as specified by your SMTP host.
* An email template
* The list of Secret Santas
* Optionally a lookup of anyone who should not be someone else's Secret Santa

### 3. Perform a Dry Run

$ ./secretsantamailer.py

This will read the configuration file and perform a "dry run" of the various pairings between Secret Santas and recipients. It will generate an output file as specified by the secret_santa_record_file setting in config.py.

This record file is saved as secret-santa-record-file.txt by default.

### 4. Configure the SMTP Settings

This script relies on a simple SMTP method of sending emails, and the SMTP setting in config.py will depend on your preffered service to use.

Various SMTP  server options are available. A few popular options include:
* Sendinblue - Free 300 emails/day
* Mailjet - Free 200 emails/day
* SendGrid - Free 100 emails/day
* Amazon SES

#### Test Your SMTP Configuration

Send a test email to confirm that the SMTP configuration is set up correctly:

$ ./secretsantamailer.py --send-test-email exampleuser@examplecompany.gov

If it runs without any errors, then you're ready to send the Secret Santa emails.

### 5. Send the Emails

$ ./secretsantamailer.py --official

This will dispatch the emails and record what emails it sent to the file specified by the secret_santa_record_file setting in config.py.

It will sequentially send emails to everyone.

### Wish List

* Add support for allowing a recipient to have a gift "wish list" that may be added in an email.
