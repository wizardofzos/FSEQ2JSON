FSEQ2JSON
=========

Sending your space delimited Sequential File as a JSON to a WebServer

# Use Case
So, your local systems programmers (or maybe you yourself) have written up some pretty neat code producing 
'management information' in a so-called Sequential File.

Suppose, for arguments' sake this data (resulting or intermediate) is stored in a space delimeted format like for example say a report on VOLUME USAGE (to be used in storage management reports).

As an example, it might look just like this (any likeliness to VOLSER-names used at your site is purely coincidental!)

    VOLSER VOLUME_TYPE USED_CYLS  FREE_CYLS
    SP1200 3390-1           1000       2390       
    SP1201 3390-1            500       2890
    
This list (dataset, sequential file) going on liek that....

Wouldn't it be great if you could run this dataset through a little JOB transforming it into a JSON-structure like below:

    {
     "results"  : 
     [
      {
       "VOLSER" : "SP1200",
       "VOLUME_TYPE" : "3390-1",
       "USED_CYLS" : "1000",
       "FREE_CYLS" : "2390"
      },
      {
       "VOLSER" : "SP1201",
       "VOLUME_TYPE" : "3390-1",
       "USED_CYLS" : "500",
       "FREE_CYLS" : "2890"
      }
     ]
    }

Now you could just use this little JSON to present the data via some 'html/javascript/jsonparsing' so this data can be made visible within your organisation without people having to go into this tedious world called 3270 to browse this data via ISPF;3;4, or downloading it and bringing it into MickeySoft Excel :)


