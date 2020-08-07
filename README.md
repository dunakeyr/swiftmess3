Parses ISO15022 into python tuples. Since this is a fork I wasn't able to test all the MT file types, but I tested it with a MT-535 file successfully.

```
import swiftmess3
from io import StringIO

swift_message = """{1:F01AAAAGRA0AXXX0057000289}{2:O1030919010321BBBBGRA0AXXX00570001710103210920N}{3:{108:MT103 003 OF 045}{121:c8b66b47-2bd9-48fe-be90-93c2096f27d2}}{4:\r\n:20:5387354\r\n:23B:CRED\r\n:23E:PHOB/20.527.19.60\r\n:32A:000526USD1101,50\r\n:33B:USD1121,50\r\n:50K:FRANZ HOLZAPFEL GMBH\r\nVIENNA\r\n:52A:BKAUATWW\r\n:59:723491524\r\nC. KLEIN\r\nBLOEMENGRACHT 15\r\nAMSTERDAM\r\n:71A:SHA\r\n:71F:USD10,\r\n:71F:USD10,\r\n:72:/INS/CHASUS33\r\n-}"""

data = StringIO(swift_message)

for obj in swiftmess3.structuredItems(data):
  print(obj)
```
