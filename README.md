Brute Force Login Prevention System

This project implements a secure and robust login system using Python, designed to protect against brute-force attacks. The system incorporates multiple layers of defense, including CAPTCHA, temporary lockouts, permanent IP blocking, rate limiting, and email alerts.

Features

	1.	Temporary Lockout:
	•	Users are temporarily locked out after exceeding the allowed number of failed login attempts (MAX_ATTEMPTS).
	•	Lockout duration is defined by the LOCKOUT_TIME parameter.
	2.	Permanent IP Blocking:
	•	IP addresses are permanently blocked after a certain number of failed attempts (PERMANENT_BLOCK_THRESHOLD).
	3.	Rate Limiting:
	•	Limits the number of login attempts per minute (RATE_LIMIT) to prevent excessive retries.
	4.	CAPTCHA Verification:
	•	A simple CAPTCHA is presented after repeated failed attempts (CAPTCHA_THRESHOLD) to ensure the user is human.
	5.	Email Alerts:
	•	Sends email alerts to administrators when an IP is permanently blocked due to suspicious activity.

System Parameters

Parameter	Description	Default Value
LOCKOUT_TIME	Duration of temporary lockout in seconds.	60 seconds
MAX_ATTEMPTS	Max failed attempts before a temporary lockout.	5 attempts
PERMANENT_BLOCK_THRESHOLD	Failed attempts before permanent IP blocking.	10 attempts
RATE_LIMIT	Max login attempts allowed per minute.	10 attempts/min
CAPTCHA_THRESHOLD	Failed attempts before CAPTCHA is required.	3 attempts

Technologies Used

	•	Python: Core programming language for the system.
	•	Libraries:
	•	time: Manages timeouts and rate limits.
	•	random: Generates simple CAPTCHA challenges.
	•	smtplib: Sends email alerts to administrators.
	•	collections.defaultdict: Tracks failed attempts by IP.

How to Run

	1.	Clone this repository:

git clone https://github.com/yourusername/BruteForceLoginPrevention.git
cd BruteForceLoginPrevention


	2.	Install Python (if not already installed).
	3.	Run the script:

python brute_force_login_prevention.py


	4.	Simulate login attempts by following the prompts.

Usage

	1.	Enter a username and password to simulate login attempts.
	2.	After repeated failed attempts:
	•	A CAPTCHA challenge will appear.
	•	Temporary lockout or rate limit messages may occur.
	•	IPs exceeding the permanent block threshold will be blocked.
	3.	Admins will receive an email alert if a suspicious IP is permanently blocked.

Example Outputs

	•	Successful Login:

[SUCCESS] Login successful!


	•	Failed Login:

[FAILED] Invalid username or password.


	•	CAPTCHA Verification:

CAPTCHA: What is 5 + 7?
Enter CAPTCHA answer: 12


	•	Temporary Lockout:

[LOCKOUT] Too many failed attempts. Try again after the lockout period.


	•	Permanent Block and Alert:

[PERMANENT BLOCK] IP 192.168.1.1 permanently blocked.
[ALERT] Email sent to admin about IP: 192.168.1.1 being permanently blocked.



Customization

You can modify system parameters to adjust the security settings:

	•	Change the LOCKOUT_TIME, MAX_ATTEMPTS, or other parameters to fit your requirements.
	•	Replace the email alert configuration (smtplib) with your own SMTP server details.

Potential Enhancements

	1.	Database Integration:
Use a database (e.g., SQLite, MySQL) to store login attempts and blocked IPs persistently.
	2.	Advanced CAPTCHA:
Replace the simple CAPTCHA with Google reCAPTCHA or other robust solutions.
	3.	Web Integration:
Convert the script into a web-based application using frameworks like Flask or Django.

License

This project is open-source and available under the MIT License.

Feel free to modify and enhance the system to suit your specific needs!