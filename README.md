def longest_common_prefix(strs):
    if not strs:
        return ""
    
    # Start with the first string as the prefix
    prefix = strs[0]
    
    # Compare the prefix with each string in the list
    for string in strs[1:]:
        # Update the prefix by comparing with the current string
        while string[:len(prefix)] != prefix and prefix:
            prefix = prefix[:-1]
        # If at any point the prefix is reduced to an empty string, return ""
        if not prefix:
            return ""
    
    return prefix

# Example usage
input_strs = ["flower", "flow", "flight"]
output = longest_common_prefix(input_strs)
print("Output:", output)  # Output: "fl"
https://meet.google.com/zwe-xijv-qrj

def calculateScore(text, prefixString, suffixString):
    def longest_suffix_prefix_match(text, prefixString, suffixString):
        # Find longest match for prefix score
        max_prefix_score = 0
        prefix_match = ""
        for i in range(len(prefixString)):
            if text.startswith(prefixString[i:]):
                score = len(prefixString) - i
                if score > max_prefix_score:
                    max_prefix_score = score
                    prefix_match = prefixString[i:]

        # Find longest match for suffix score
        max_suffix_score = 0
        suffix_match = ""
        for i in range(1, len(suffixString) + 1):
            if text.endswith(suffixString[:i]):
                score = i
                if score > max_suffix_score:
                    max_suffix_score = score
                    suffix_match = suffixString[:i]

        return prefix_match, suffix_match, max_prefix_score, max_suffix_score

    max_score = 0
    result = text

    for i in range(len(text)):
        for j in range(i + 1, len(text) + 1):
            substring = text[i:j]
            prefix_match, suffix_match, prefix_score, suffix_score = longest_suffix_prefix_match(substring, prefixString, suffixString)
            current_score = prefix_score + suffix_score
            if current_score > max_score or (current_score == max_score and substring < result):
                max_score = current_score
                result = substring

    return result

# Sample Input
text = "nothing"
prefixString = "bruno"
suffixString = "ingenious"

# Expected Output: "nothing"
print(calculateScore(text, prefixString, suffixString))

# Sample Input
text = "ab"
prefixString = "b"
suffixString = "a"

# Expected Output: "a"
print(calculateScore(text, prefixString, suffixString))


To solve the problem of finding the substring of `text` that has the highest combined prefix and suffix match scores, we need to implement a function that calculates these scores and returns the appropriate substring. Here's a Python implementation:

```python
def calculateScore(text, prefixString, suffixString):
    def longest_suffix_prefix_match(text, prefixString, suffixString):
        # Find longest match for prefix score
        max_prefix_score = 0
        prefix_match = ""
        for i in range(len(prefixString)):
            if text.startswith(prefixString[i:]):
                score = len(prefixString) - i
                if score > max_prefix_score:
                    max_prefix_score = score
                    prefix_match = prefixString[i:]

        # Find longest match for suffix score
        max_suffix_score = 0
        suffix_match = ""
        for i in range(1, len(suffixString) + 1):
            if text.endswith(suffixString[:i]):
                score = i
                if score > max_suffix_score:
                    max_suffix_score = score
                    suffix_match = suffixString[:i]

        return prefix_match, suffix_match, max_prefix_score, max_suffix_score

    max_score = 0
    result = text

    for i in range(len(text)):
        for j in range(i + 1, len(text) + 1):
            substring = text[i:j]
            prefix_match, suffix_match, prefix_score, suffix_score = longest_suffix_prefix_match(substring, prefixString, suffixString)
            current_score = prefix_score + suffix_score
            if current_score > max_score or (current_score == max_score and substring < result):
                max_score = current_score
                result = substring

    return result

# Sample Input
text = "nothing"
prefixString = "bruno"
suffixString = "ingenious"

# Expected Output: "nothing"
print(calculateScore(text, prefixString, suffixString))

# Sample Input
text = "ab"
prefixString = "b"
suffixString = "a"

# Expected Output: "a"
print(calculateScore(text, prefixString, suffixString))
```

### Explanation:
1. **Function `longest_suffix_prefix_match`:** 
    - This function finds the longest suffix of `prefixString` that matches the beginning of `text` and the longest prefix of `suffixString` that matches the end of `text`.
    - It iterates over possible suffixes and prefixes to find the longest matching segments.

2. **Function `calculateScore`:**
    - This function iterates over all possible substrings of `text`.
    - For each substring, it calculates the prefix and suffix scores using `longest_suffix_prefix_match`.
    - It keeps track of the substring with the highest combined prefix and suffix scores.
    - In case of a tie, it returns the lexicographically smaller substring.

### Key Points:
- The approach ensures that the substring with the highest combined score is found.
- The implementation ensures that the correct substring is returned even if there are ties in scores by comparing lexicographically.
- The solution handles the edge cases mentioned, including when prefix and suffix overlap.

This code should solve the given problem efficiently within the constraints provided.


