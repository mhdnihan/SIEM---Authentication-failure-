**Authentication Failure Investigation**

Detection: Windows Security Event ID 4625
Wazuh Rule: 60122
Rule Level: 5

A failed authentication event was generated on the Windows 11 endpoint and detected by Wazuh. The event targeted the Nihan account and used Logon Type 2 (Interactive).

Investigation findings:

* Source IP: 127.0.0.1
* Status: 0xc000006d
* SubStatus: 0xc000006a
* Authentication failure reason: Incorrect password

The source address 127.0.0.1 indicates that the authentication attempt originated locally from the Windows endpoint. The 0xc000006a substatus indicates that the password was incorrect.

The event was intentionally generated during testing by entering an incorrect password. Therefore, the activity was assessed as benign test activity, rather than a genuine unauthorized access attempt.

SOC workflow demonstrated:

Log → Detection → Alert → Triage → Investigation → Evidence → Verdict
