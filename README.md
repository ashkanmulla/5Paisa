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
