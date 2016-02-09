## Receive email notifications for errors in edi

When bots runs scheduled, it is cumbersome to keep checking for errors in the
bots-monitor.  
It is possible to receive an email-report in case of errors.  
Configure this:

1.  Set option 'sendreportiferror' in *bots/config/bots.ini* to True.
2.  In *bots/config/settings.py* set relevant data for email, eg like:

        MANAGERS = (    #bots will send error reports to the MANAGERS
            ('name_manager', 'myemailaddress@gmail'),
            )
        EMAIL_HOST = 'smtp.gmail.com'             #Default: 'localhost'
        EMAIL_PORT = '587'             #Default: 25
        EMAIL_USE_TLS = True       #Default: False
        EMAIL_HOST_USER = 'username'        #Default: ''. Username to use for the SMTP server defined in EMAIL_HOST. If empty, Django won't attempt authentication.
        EMAIL_HOST_PASSWORD = '*******'    #Default: ''. PASSWORD to use for the SMTP server defined in EMAIL_HOST. If empty, Django won't attempt authentication.
        SERVER_EMAIL = 'botserrors@gmail.com'           #Sender of bots error reports. Default: 'root@localhost'
        EMAIL_SUBJECT_PREFIX = ''   #This is prepended on email subject.

3.  To test if it works OK, restart the bots-webserver and
    *bots-monitor-\>Systasks-\>Send test report*. (I know, the
    restarting is annoying.).

Note: Email notifications are not sent while running [acceptance
tests](DeploymentAcceptance.md).

