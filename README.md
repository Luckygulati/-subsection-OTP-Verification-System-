Project Title: OTP Verification System
Problem Statement:
You are tasked with developing an OTP (One-Time Password) verification system in Python. The system should generate a 6-digit OTP and send it to the user's email address for verification. Upon receiving the OTP, the user should enter it into the system for validation. If the entered OTP matches the generated OTP, access should be granted; otherwise, access should be denied.
Project Requirements:
•	Implement a function to generate a 6-digit OTP randomly.
•	Develop a function to simulate sending the OTP to the user's email address.
•	Create a function to prompt the user to enter the OTP received in their email.
•	Implement a function to verify if the entered OTP matches the generated OTP.
•	Ensure proper error handling and user-friendly prompts throughout the system.
•	Allow the user to retry OTP entry in case of incorrect input.
Project Deliverables:
•	Python script containing the implementation of the OTP verification system.
•	Documentation explaining the functionality of each function, how to run the program, and any dependencies required.
•	Test cases to ensure the system functions correctly under various scenarios, including correct and incorrect OTP entries.
•	Optionally, you can create a simple GUI interface for the OTP verification system to enhance user experience.
Project Evaluation:
Your project will be evaluated based on the following criteria:
•	Correctness and functionality of the OTP generation, sending, and verification process.
•	Code quality, including adherence to Python best practices, readability, and documentation.
•	Error handling and user interaction aspects of the system.
•	Robustness and reliability of the system under different scenarios.
•	Optional: Creativity and usability of the GUI interface (if implemented).
Note: Ensure that you handle sensitive information (such as email addresses and OTPs) securely and responsibly, and avoid hardcoding any sensitive data or credentials in your code.
Summary 
The goal of this project was to develop a secure OTP (One-Time Password) verification system in
Python. The system generates a 6-digit OTP and sends it to the user’s email for verification. The
user then inputs the OTP into the system for validation. If the entered OTP matches the generated
OTP, access is granted; otherwise, access is denied. This project ensures a reliable method of
verifying user identity for secure transactions.

○ Developed a secure OTP verification system in Python.
○ Generated and sent 6-digit OTPs to user emails for verification.
○ Implemented OTP verification, error handling, and retry mechanisms.
○ Enhanced user interaction and security with robust error handling.


import random

def generate_otp():
    """Generate a 6-digit OTP."""
    otp = ''.join(str(random.randint(0, 9)) for _ in range(6))
    return otp

def send_email(email, generated_otp):
    """Send OTP to the user's email address."""
    print(f"Email sent for OTP verification: {generated_otp}")  # Simulating email sending

def verify_otp(generated_otp):
    """Verify if the entered OTP matches the generated OTP."""
    entered_otp = input("Enter the OTP: ")
    if len(entered_otp) != 6 or not entered_otp.isdigit():
        raise ValueError("Please enter a valid 6-digit OTP.")
    return generated_otp == entered_otp

def main():
    max_attempts = 3
    for _ in range(max_attempts):
        generated_otp = generate_otp()
        try:
            send_email("user@example.com", generated_otp)  # Replace with user's email
            if verify_otp(generated_otp):
                print("OTP verified successfully! Access granted.")
                break
            else:
                print("Incorrect OTP. Please try again.")
except ValueError as e:
            print(e)
    else:
        print("Maximum attempts exceeded. Please try again later.")

if __name__ == "__main__":
    main()    
