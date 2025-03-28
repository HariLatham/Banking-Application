# Web-Application
#Number Programs implementation :  Using Python and Streamlit  
#"Integrated a Number program system with Python and Streamlit to get proper output data in real-time


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
