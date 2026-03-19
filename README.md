class Solution:
    def solution(self, N):
        # Convert integer to binary string (remove '0b' prefix)
        binary_string = bin(N)[2:]

        max_gap = 0
        current_gap = 0
        in_gap = False

        # Loop through each bit
        for bit in binary_string:
            if bit == '1':
                if in_gap:
                    # End of a gap
                    if current_gap > max_gap:
                        max_gap = current_gap
                    current_gap = 0
                in_gap = True
            else:
                if in_gap:
                    current_gap += 1

        return max_gap





## define fobonacci 

def fibonacci(n):
    """
    Generate and print the first n Fibonacci numbers.

    Fibonacci sequence:
    0, 1, 1, 2, 3, 5, 8, ...

    Parameters:
    n (int): Number of terms to generate

    Returns:
    None
    """

    # Initialize the first two numbers
    a, b = 0, 1

    # Loop n times
    for _ in range(n):
        print(a, end=" ")  # Print current number
        a, b = b, a + b    # Update values

# Example usage
fibonacci(10)
