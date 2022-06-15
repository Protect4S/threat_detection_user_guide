# MaxDB

To connect your Central Protect4S TD System to Satellite Systems that have a MaxDB type database, follow the instructions mentioned in:

* SAP Note: [822271 - FAQ: SAP MaxDB client software](http://service.sap.com/sap/support/notes/822271)
* SAP Note: [649814 - Updating the SAP MaxDB/liveCache client software](http://service.sap.com/sap/support/notes/649814).

Don't forget to add the environment variables as mentioned in note 649814 like e.g. in the RZ10 instance profile like:\
SETENV\_01 LD\_LIBRARY\_PATH=/sapdb/clients/\<SID>/lib:/sapdb/clients/\<SID>/lib/lib64:$(DIR\_LIBRARY):%(LD\_LIBRARY\_PATH)\
SETENV\_04 PATH=/sapdb/clients/\<SID>/bin:/sapdb/clients/\<SID>/pgm:/sapdb/programs/pgm:/sapdb/programs/bin:$(DIR\_EXECUTABLE):%(PATH)\
Execute\_00 immediate $(DIR\_CT\_RUN)$(DIR\_SEP)sapcpe$(FT\_EXE) pf=$(\_PF)
