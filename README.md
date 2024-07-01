# SeaCMS has a command execution vulnerability
SeaCMS has a command execution vulnerability

1. Download the latest source code of SeaCMS.
2. Open the file `64685b/admin_weixin.php` for code auditing.
3. ![image](https://github.com/Q1M0Sec/seacms/assets/102501236/e8b69cf9-4119-49c0-9f4d-37b85d749578)
4. There is arbitrary file write vulnerability in the `$dpic` variable. Other variables received have filtered characters.
5. Trace the code.
6. ![image](https://github.com/Q1M0Sec/seacms/assets/102501236/d8aaefa7-6e14-473a-8d5f-7763c880cc67)
7. File writing is controlled at this point.
8.![image](https://github.com/Q1M0Sec/seacms/assets/102501236/8bbe26c6-b108-423f-887b-a9e9c63d89a6)
9.![image](https://github.com/Q1M0Sec/seacms/assets/102501236/d6b18293-a931-452a-8d42-b6e93df031b9)
10.![image](https://github.com/Q1M0Sec/seacms/assets/102501236/9f43efa2-2435-423c-b505-5853652a84da)
