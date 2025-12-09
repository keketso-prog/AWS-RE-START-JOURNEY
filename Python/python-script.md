I worked through a Python programming lab where I created a script to identify prime numbers between 1 and 250, learning about functions, loops, and file handling. Here's what I did.
# Creating the Python Script
I created a Python script file using the nano text editor by executing nano prime_numbers.py in the Linux terminal.
# Writing the Prime Number Logic
I wrote a prime-checking function that tests whether a number is prime by checking for divisibility from 2 up to the number itself. Then I implemented the main logic using a loop to iterate through numbers 1 to 250, applying the prime-checking function to each number and storing the results in a list.
# Adding Output and File Writing
I added output functionality to display the prime numbers in the console using the print() function. Then I configured file writing to save results to results.txt using Python's file handling methods (open(), write(), and close()).
# Saving and Running the Script
I saved the script in nano by pressing Ctrl+X, confirming with Y, and pressing Enter. Then I executed the script using the command python3 prime_numbers.py.
# Verifying the Results
I verified the results by viewing the contents of results.txt using the cat command, which confirmed that all 53 prime numbers were successfully identified and stored. I documented the script location by obtaining the absolute path using realpath prime_numbers.py for future reference.

<img width="1577" height="826" alt="Screenshot (1733)" src="https://github.com/user-attachments/assets/3170fe59-339d-4ea0-aca1-783f29e14007" />
<img width="652" height="420" alt="Screenshot (1735)" src="https://github.com/user-attachments/assets/bd20d923-e4be-4add-9dfd-e20092bd46e5" />
<img width="654" height="420" alt="Screenshot (1736)" src="https://github.com/user-attachments/assets/09e620c0-1259-4a3a-a643-0a8ef11e5cce" />
<img width="718" height="515" alt="Screenshot (1748)" src="https://github.com/user-attachments/assets/d4282226-fe37-4b3e-9aa5-3d976d871d5d" />
<img width="658" height="412" alt="Screenshot (1738)" src="https://github.com/user-attachments/assets/682da673-1cae-4300-a1be-9b75e12bb9d8" />
<img width="665" height="417" alt="Screenshot (1739)" src="https://github.com/user-attachments/assets/a02a8030-ea68-44ca-b3fb-618bb57219ba" />
<img width="666" height="419" alt="Screenshot (1745)" src="https://github.com/user-attachments/assets/5bb44a51-c139-433d-bc5a-b006899b7eda" />
<img width="657" height="414" alt="Screenshot (1746)" src="https://github.com/user-attachments/assets/33d40f54-2e0c-4d15-b71b-9f39d1623ddb" />
<img width="657" height="415" alt="Screenshot (1747)" src="https://github.com/user-attachments/assets/fe829c00-734e-44bc-8120-524168c81420" />

 The script successfully identified 53 prime numbers and saved them to the results file as required.
 # CHALLENGES
 File Handling Syntax: I struggled with properly closing the file after writing to it. I forgot to include the close() method initially, which could have caused issues with data not being saved properly to results.txt.
## WHAT I LEARNED
Here's what I learned from this challenge:

- I created a Python script using the nano text editor and learned the importance of proper indentation and syntax in Python.
- I implemented a prime number algorithm that identifies all prime numbers between 1 and 250 by checking for divisibility.
- I used Python's file handling methods to write results to a text file for permanent storage.
# OVERALL
I learned how to write and execute Python scripts on Linux, process numerical data, and save output to external files using the command line
## Lab Complete 🎓

