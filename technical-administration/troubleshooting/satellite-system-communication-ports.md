# Satellite system communication ports

The Protect4S TD solution communicates with its monitored systems using the following types of connections and ports:

| **Connection Type**          | **Port (range)**                                        | **Description**                                          | **Used for**       |
| ---------------------------- | ------------------------------------------------------- | -------------------------------------------------------- | ------------------ |
| ABAP system connection       | 3300-3399                                               | CPIC and RFC communication                               | SAP gateway        |
| ABAP system connection       | 4800-4899                                               | SNC Secured SAP gateway                                  | Secure SAP Gateway |
| Java system information      | 5xx00                                                   | HTTP communication. xx = SAP instance number (00 .. 99)  | Java HTTP port     |
| Java system information      | 5xx01                                                   | HTTP communication. xx = SAP instance number (00 .. 99)  | HTTP over SSL      |
| Database connection          | 1433                                                    | Default port (other port possible)                       | MSSQL DB           |
| Database connection          | 1521/1527                                               | Default port (other port possible)                       | Oracle             |
| Database connection          | 5912                                                    | Default port (other port possible)                       | DB2                |
| Database connection          | 5000/5001                                               | Default port (other port possible)                       | SAP Sybase         |
| Database connection          | [Port 3xx15 See SCN](https://help.sap.com/viewer/ports) | Default port (other port possible)                       | SAP Hana           |
| Database connection          | 7210                                                    | Default port (other port possible)                       | MaxDB              |
| SAPControl webservice        | 5xx13                                                   | HTTP communication. xx = SAP instance number (00 .. 99)  | SOAP over HTTP     |
| SAPControl secure webservice | 5xx14                                                   | HTTPS communication. xx = SAP instance number (00 .. 99) | SOAP over HTTS     |

More details can be found in the SAP document: [TCP/IP Ports Used by SAP Applications.](http://www.sdn.sap.com/irj/scn/go/portal/prtroot/docs/library/uuid/4e515a43-0e01-0010-2da1-9bcc452c280b?QuickLink=index\&overridelayout=true&42472931642836)
