**Challenge Lab: Python Scripting Exercise**

def is_prime(num):

\"\"\"

Checks if a number is prime.

A prime number is a natural number greater than 1 that has no positive
divisors other than 1 and itself.

\"\"\"

if num \<= 1:

return False

for i in range(2, int(num\*\*0.5) + 1):

if num % i == 0:

return False

return True

def find_and_store_primes(start, end, filename=\"results.txt\"):

\"\"\"

Finds prime numbers within a given range and stores them in a specified
file.

\"\"\"

prime_numbers = \[\]

for number in range(start, end + 1):

if is_prime(number):

prime_numbers.append(number)

print(f\"Prime numbers between {start} and {end}:\")

print(prime_numbers)

with open(filename, \'w\') as f:

for prime in prime_numbers:

f.write(f\"{prime}\\n\")

print(f\"\\nPrime numbers have been stored in \'{filename}\'.\")

\# Execute the function to find and store primes

find_and_store_primes(1, 250)

\# Verification step (optional, but good for testing)

print(\"\\nVerifying the contents of results.txt\...\")

try:

with open(\"results.txt\", \'r\') as f:

content = f.read()

print(\"Content of results.txt:\")

print(content)

except FileNotFoundError:

print(\"Error: results.txt not found.\")
