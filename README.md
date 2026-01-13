def longestPalindrome(s):
    if not s:
        return ""

    start = 0
    max_length = 1

    for i in range(len(s)):

        # Case 1: Odd length palindrome
        left = i
        right = i
        while left >= 0 and right < len(s) and s[left] == s[right]:
            if right - left + 1 > max_length:
                start = left
                max_length = right - left + 1
            left -= 1
            right += 1

        # Case 2: Even length palindrome
        left = i
        right = i + 1
        while left >= 0 and right < len(s) and s[left] == s[right]:
            if right - left + 1 > max_length:
                start = left
                max_length = right - left + 1
            left -= 1
            right += 1

    return s[start:start + max_length]


# -------- Main Program --------
s = input("Enter a string: ")
result = longestPalindrome(s)
print("Longest Palindromic Substring:", result)
