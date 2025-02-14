# Banking-Application
#Banking System Implementation:  Using MySQL Database and python  "Integrated a banking system with MySQL to store user data securely and manage  transactions in real-time.
import streamlit as st


# Helper functions for various number properties
def is_armstrong(num):
    num_str = str(num)
    num_digits = len(num_str)
    sum_of_powers = sum(int(digit) ** num_digits for digit in num_str)
    return sum_of_powers == num


def is_strong(num):
    def factorial(n):
        if n == 0 or n == 1:
            return 1
        else:
            return n * factorial(n - 1)

    return num == sum(factorial(int(digit)) for digit in str(num))


def fibonacci_series(n):
    series = [0, 1]
    while series[-1] < n:
        series.append(series[-1] + series[-2])
    return series


def is_perfect_square(num):
    return int(num ** 0.5) ** 2 == num


def is_perfect(num):
    divisors_sum = sum(i for i in range(1, num) if num % i == 0)
    return divisors_sum == num


def is_happy(num):
    def sum_of_squares(n):
        return sum(int(digit) ** 2 for digit in str(n))

    seen = set()
    while num != 1 and num not in seen:
        seen.add(num)
        num = sum_of_squares(num)
    return num == 1


def is_harshad(num):
    digit_sum = sum(int(digit) for digit in str(num))
    return num % digit_sum == 0


# Streamlit UI components
st.title('Number Programs')
no = st.number_input('Enter the number', min_value=0)
reverse_btn = st.button('REVERSE', type='primary')
factorial_btn = st.button('FACTORIAL', type='primary')
palindrome_btn = st.button('PALINDROME', type='primary')
sum_digits_btn = st.button('SUM OF DIGITS', type='primary')
digit_count_btn = st.button('NUMBER OF DIGITS', type='primary')
armstrong_btn = st.button('ARMSTRONG NUMBER', type='primary')
strong_btn = st.button('STRONG NUMBER', type='primary')
fibonacci_btn = st.button('FIBONACCI SERIES', type='primary')
perfect_square_btn = st.button('PERFECT SQUARE', type='primary')
perfect_num_btn = st.button('PERFECT NUMBER', type='primary')
happy_num_btn = st.button('HAPPY NUMBER', type='primary')
harshad_num_btn = st.button('HARSHAD NUMBER', type='primary')

# Reverse the number
if reverse_btn:
    reverse_no = str(no)[::-1]  # Reverse the string of the number
    st.success(f'Reversed number is: {reverse_no}')

# Factorial of the number
elif factorial_btn:
    temp = no
    fact = 1
    while temp > 0:
        fact = fact * temp
        temp = temp - 1
    st.success(f'Factorial of {no} is: {fact}')

# Palindrome check
elif palindrome_btn:
    str_no = str(no)
    if str_no == str_no[::-1]:
        st.success(f'{no} is a palindrome')
    else:
        st.error(f'{no} is not a palindrome')

# Sum of digits of the number
elif sum_digits_btn:
    sum_digits = sum(int(digit) for digit in str(no))  # Sum of digits
    st.success(f'Sum of digits of {no} is: {sum_digits}')

# Number of digits in the number
elif digit_count_btn:
    num_digits = len(str(no))  # Count the digits in the number
    st.success(f'Number of digits in {no} is: {num_digits}')

# Armstrong Number check
elif armstrong_btn:
    if is_armstrong(no):
        st.success(f'{no} is an Armstrong number')
    else:
        st.error(f'{no} is not an Armstrong number')

# Strong Number check
elif strong_btn:
    if is_strong(no):
        st.success(f'{no} is a Strong number')
    else:
        st.error(f'{no} is not a Strong number')

# Fibonacci Series
elif fibonacci_btn:
    series = fibonacci_series(no)
    st.success(f'Fibonacci series up to {no} is: {series}')

# Perfect Square check
elif perfect_square_btn:
    if is_perfect_square(no):
        st.success(f'{no} is a Perfect Square')
    else:
        st.error(f'{no} is not a Perfect Square')

# Perfect Number check
elif perfect_num_btn:
    if is_perfect(no):
        st.success(f'{no} is a Perfect Number')
    else:
        st.error(f'{no} is not a Perfect Number')

# Happy Number check
elif happy_num_btn:
    if is_happy(no):
        st.success(f'{no} is a Happy Number')
    else:
        st.error(f'{no} is not a Happy Number')

# Harshad Number check
elif harshad_num_btn:
    if is_harshad(no):
        st.success(f'{no} is a Harshad Number')
    else:
        st.error(f'{no} is not a Harshad Number')
