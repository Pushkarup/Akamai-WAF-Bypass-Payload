# Akamai WAF Bypass Payload Documentation

### Author: Pushkar Upadhyay
- Email: thepushkar24@gmail.com
- GitHub: [Pushkarup](https://github.com/Pushkarup)
- LinkedIn: [Pushkar Upadhyay](https://www.linkedin.com/in/pushkar-upadhyay-24p/)


## Overview

This documentation provides an explanation and usage instructions for an Akamai WAF (Web Application Firewall) bypass payload. The payload is designed to execute a Cross-Site Scripting (XSS) attack by exploiting a vulnerability in the target application's security controls, specifically targeting an Akamai WAF.

**Note:** The use of this payload or any other hacking techniques without proper authorization is illegal and unethical. Ensure that you have the necessary permissions and legal consent before performing any security testing or demonstrating vulnerabilities.

## Payload Details

Payload: `%22onmouseover=window[%27al%27%2B%27er%27%2B([%27t%27,%27b%27,%27c%27][0])](document[%27cooki%27%2B(['e','c','z'][0])]);%22`

### Payload Explanation

The payload is a URL-encoded JavaScript code that leverages the `onmouseover` event to trigger a JavaScript function. It starts by defining a variable that represents the `alert` function using concatenation: `%27al%27%2B%27er%27%2B([%27t%27,%27b%27,%27c%27][0])`. This is done to evade detection by Akamai WAF's security rules.

The payload then calls the `alert` function with the `document.cookie` property as an argument. This retrieves the user's cookies and displays them in an alert dialog.

### How the Payload Works

When the target application renders the payload within an HTML element that supports the `onmouseover` event, such as a link or an image, the JavaScript code is executed. Upon triggering the `onmouseover` event, the payload calls the `alert` function with the `document.cookie` property, which displays the user's cookies.

### Usage Instructions

To use this payload, follow the steps below:

1. Identify the target application protected by Akamai WAF.
2. Locate an input field or an HTML element that supports the `onmouseover` event.
3. Insert the payload into the appropriate location, URL-encoded, within the HTML element or input field.
4. Trigger the `onmouseover` event, either by hovering over the element or submitting the form if the payload is placed within an input field.
5. If the payload is successful, an alert dialog should pop up displaying the user's cookies.

### Security Implications

Successful execution of this payload can lead to various security risks, including session hijacking, data theft, and unauthorized actions on behalf of the user. By retrieving and displaying the user's cookies, an attacker can potentially gain unauthorized access to the user's accounts or sensitive information.

### Countermeasures

To protect against XSS attacks and Akamai WAF bypass attempts, it is recommended to implement the following security measures:

- Input validation: Validate and sanitize all user-generated input to prevent malicious code injection.
- Output encoding: Properly encode user-generated output to prevent script execution.
- Web Application Firewall: Utilize a robust WAF that is regularly updated with the latest security rules to detect and prevent XSS attacks.

### Legal and Ethical Considerations

It is important to use hacking techniques responsibly and ethically. Unauthorized penetration testing or exploiting vulnerabilities without proper authorization is illegal and can have severe consequences. Always ensure that you have the necessary permissions and legal consent before performing any security testing or demonstrating vulnerabilities.
