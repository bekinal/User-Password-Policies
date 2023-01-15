<h1>User Password Policies</h1>

<h2>Description</h2>
Project consists of using Active Directory Group Policy Management to configure password policies for users in the domain.
<br />


<h2>Utilities Used</h2>

- <b>VirtualBox</b> 
- <b>Group Policy Management</b>

<h2>Environments Used </h2>

- <b>Windows Server 2016</b>
- <b>Windows 10</b>

<h2>Create and Apply Password Group Policy:</h2>
Open Group Policy Management in the domain controller. Naviagate to Default Domain Policy, right-click and select Edit: <br/>
<img src="https://imagizer.imageshack.com/img922/5481/XwwY7o.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Navigate to Password Policy and double click Minimum Password Length: <br/>
<img src="https://imagizer.imageshack.com/img922/2571/MQsCRw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select Define this policy setting and set the number of characters to 10: <br/>
<img src="https://imagizer.imageshack.com/img923/2154/tiNUes.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Go to Password must meet complexity requirements and verify that the policy is enabled. If not, select Define this policy setting, select Enabled, click Apply, and click OK: <br/>
<img src="https://imagizer.imageshack.com/img924/7524/IvjLZP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Double-click the Maximum password age, select Define this policy setting and set it to 30 days. Click apply and OK: <br/>
<img src="https://imagizer.imageshack.com/img924/5853/x0DNzD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
In the next window, click ok: <br/>
<img src="https://imagizer.imageshack.com/img922/4223/Tuauqo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
In order to test this, we need to set the Minimum password age to zero. Double click minimum password age and select Define this policy setting. Set the value to 0 days: <br/>
<img src="https://imagizer.imageshack.com/img922/2846/b2Zbk9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Double click Enforce Password history, select Define this policy setting. Change to 3.: <br/>
<img src="https://imagizer.imageshack.com/img923/4091/CjLWDU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Navigate to Account lockout threshold: <br/>
<img src="https://imagizer.imageshack.com/img924/3237/feD4GR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Configure the account lockout policy with an account lockout threshold of five invalid logon attempts: <br/>
<img src="https://imagizer.imageshack.com/img924/1227/EPAJcm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Click OK: <br/>
<img src="https://imagizer.imageshack.com/img924/6843/Z4JLZy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Double click Account lockout duration and change the value to 5 minutes. Click apply and OK: <br/>
<img src="https://imagizer.imageshack.com/img924/4724/Zsqlcm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Note the rule and click OK: <br/>
<img src="https://imagizer.imageshack.com/img922/6889/etmMMf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />




<h2>Verify Password Policies:</h2>
Log into the Windows 10 client under a regular user and run "gpupdate /force": <br/>
<img src="https://imagizer.imageshack.com/img924/2693/DDN9IR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Press Ctrl+Alt+Del to change your password: <br/>
<img src="https://imagizer.imageshack.com/img923/6755/qT1vf6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Click change password!: <br/>
<img src="https://imagizer.imageshack.com/img922/5775/Jmcj8N.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Attempt to change password to Abc123!: <br/>
<img src="https://imagizer.imageshack.com/img922/1449/XbWP4A.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Verify the password does not change due to lack of requirements: <br/>
<img src="https://imagizer.imageshack.com/img923/6008/gYLPb4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Change the password to Presto123! Note that the password change is a success: <br/>
<img src="https://imagizer.imageshack.com/img922/397/J7IYIJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Log out, and force an account lockout by inputting five incorrect passwords: <br/>
<img src="https://imagizer.imageshack.com/img924/851/BkB57R.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
