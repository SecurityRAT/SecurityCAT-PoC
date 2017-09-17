# SecurityCAT-PoC
PoC implementation of SecurityCAT

SecurityCAT (Compliance Automation Tool) is a tool meant to test requirements you've defined with SecurityRAT. 
Given that the implementation depends on your requirements, it's recommended to implement your own version of SecurityCAT. 
This PoC is testing 3 requirements from OWASP ASVS 3.0.1:
 * ```ASVS_3.0.1_10.10```: Requirement 10.10 - Presence of HPKP header
 * ```ASVS_3.0.1_10.11```: Requirement 10.11 - Presence of HSTS header
 * ```ASVS_3.0.1_10.12```: Requirement 10.12 - Actived preloading for HSTS
 
 ### Prerequisities
 * Redis
 * Python libraries stated in gateway.py and microservice.py
 
 ### How to launch
1. Launch your Redis instance (local port 6379 is expected by default)
2. CD into the directory
3. Start Celery ```celery worker -A gateway.celery --loglevel=info```
4. Starting testing MS: ```python3 ./microservice.py``` 
5. Starting gateway:  ```python3 ./gateway.py``` 
