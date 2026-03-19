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
