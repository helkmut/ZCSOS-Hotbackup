		ZCSOS-Hotbackup : On-line backup with Zimbra Open Source Edition.

			Requirements:

				- To use the ZCSOS-Hotbackup directory '/opt/backup/zimbra' must exist and its owner must be the same user running the Zimbra suite;
				- Curl;
				- Follow directory struture '/opt/zimbra'.

			Controls: 

				- FULL backup: You can restore just a last backup
				- Log rotate : When the log be 10MB it will be removed if you want to keep it back up the log as well. 

            Syntax: 

				-A  : If backup or restore is for a unique account specify account in this arg

				-M  : Send status of job by e-mail

				-P  : Prefix to destiny account in restor process

				-T  : Restore(R) or Backup(B) 

				-V  : Version
	
				-h  : Help
 
                -v 1: Send to log 
                -v 0: Show log in console  
        
			Example:

			Backup full                     : /opt/zimbra/bin/zcsos-hotbackup -T B -v 1 -M mymail@mydomain.com
			Backup account                  : /opt/zimbra/bin/zcsos-hotbackup -T B -A prestesg@domain.com -v 1 -M mymail@mydomain.com
			Restore full                    : /opt/zimbra/bin/zcsos-hotbackup -T R -v 1 -M suporte@lm2.com.br
			Restore account                 : /opt/zimbra/bin/zcsos-hotbackup -T R -A prestesg@domain.com -v 1 -M mymail@mydomain.com
			Restore account with prefix     : /opt/zimbra/bin/zcsos-hotbackup -T R -A prestesg@domain.com -P test -v 1 -M mymail@mydomain.com
	
			Agent properties: /opt/zimbra/conf/zcsos-hotbackup.props

            Required APIs:

                use strict;
                use Getopt::Long;
                use POSIX;
                use File::Basename;     
				use Switch;
				use Net::SMTP; 

            Support: helkmut@gmail.com

			Author's words: Only Jesus can save him from the apocalypse.