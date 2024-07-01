# SeaCMS has multiple command execution vulnerabilities

1、Download the latest ocean cms source code

2、Open the source code 64685b/admin_weixin.php code audit

3、![image](https://github.com/Q1M0Sec/seacms/assets/102501236/b35eebae-f939-4212-9b68-e2dbf9beafe9)


4、There is arbitrary file write in the $dpic variable, and other accepted variables have filter characters

5、Tracking Code

6、![image](https://github.com/Q1M0Sec/seacms/assets/102501236/e0ccc9fc-e250-4933-a59e-4af58925e4cc)

7、File writing is controlled here

8、![image](https://github.com/Q1M0Sec/seacms/assets/102501236/23ace3cc-44ed-4ba4-a5c4-93a057f76cf9)

9、![image](https://github.com/Q1M0Sec/seacms/assets/102501236/5ebddc39-d1e3-4466-9ed2-3d254050d0bb)

10、It was found that two files were written, namely weixin.php and admin_weixin.php

11、Construct request to send

12、![image](https://github.com/Q1M0Sec/seacms/assets/102501236/88f4c174-670c-4613-9d05-6e5434817e1d)

13、First check the file changes written normally

14、![image](https://github.com/Q1M0Sec/seacms/assets/102501236/7ba6f025-8824-460e-aa79-806b67167190)

15、It is found that PHP code injection can be constructed

16、Use ");phpinfo();(" to perfectly escape the code

17、Use the constructed characters to send a request to see if the file is written successfully

18、![image](https://github.com/Q1M0Sec/seacms/assets/102501236/c1bbcdc7-ca95-41bf-bebb-45b01e1d5b5f)

19、![image](https://github.com/Q1M0Sec/seacms/assets/102501236/45788bb7-0423-4bda-8988-32bfc9075466)

20、The code is successfully written and escaped

21、Verify that the code is executed successfully

22、![image](https://github.com/Q1M0Sec/seacms/assets/102501236/5c580f84-e8cc-441a-bbb6-79159835e507)

23、Weixin.php successfully executed the code!!!

24、Check whether admin_weixin.php is also successfully written and executed

25、![image](https://github.com/Q1M0Sec/seacms/assets/102501236/dba135ad-a0ae-4468-a7b9-7c9685dd5fac)

26、Also executed successfully!!!

27、In the same code file, there are 17 variables that allow writing. They are: $dpic, $isopen, $url, $ckmov_url, $topage, $dwz, $dwztoken, $msg1a, $msg1b, $msg2a, $msg2b, $msg3a, $msg3b, $msg4a, $msg4b, $msg5a, and $msg5b.

28、These variables can all be used to write to files and execute commands using the method described earlier.


