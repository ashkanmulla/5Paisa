https://citiustech.mynexthire.io/p/#/qr/interview/conf/citiustech149611722593479193

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



YouTube

Maps

PDF Ward Con

CD Welcome to Colab

1. Scoring System.

The math scores of each studerit have been stored in the STUDENT table. Write a query to print the ID and the NAME of each of the three highest scoring students. Print the NAMES in descending order by SCORE, then ascending order by ID for matching SCORES

Input Format

STUDENT

Name

Type

Description

ID

Integer

Astudent ID in the inclusive range [1, 1000). This field is the primary key.

NAME

String

Astudent name. This field contains between and 100 characters (Inclusive)

SCORE

Float

The Math score of the student.

Output Format

The result should contain the IDs and the NAAMES of the three highest scoring students. Print the records in descending order by SCORE, then ascending order by ID for matching SCORES

STIGENT. ID STUDENT, NAME

Youlube

Maps

PDF to Word Com

CO Welcome to Colab

STUDENT, ID STUDENT NAME

Sample Input

STUDENT

ID

NAME

SCORE

1

Bob

50

2

John

65.5

3

Harry

45

4

Dick

85

5

Dev

25

6

Sid

98

7

Tom

90

8

Julia

70.5

9

Erica

81

18

Jerry

85

Sample output 
6 sid
7 tom
4 dick

Explanation

The students are arranged in the descending order of their math scores, followed by the ascending order of their ids, as shown below.

Sid

Tom

Dick

Jerry

Erica

Julia

John

Bob

Harry

Dev


https://p7tn464j.r.ap-southeast-1.awstrack.me/L0/https:%2F%2Fwww.hackerearth.com%2Fchallenges%2Ftest%2Fdata-scientist-assessment-test%2F%3Flogin=66fa35ab7b8ef616ac3748cc9233c8bb/2/010e019111882d0c-1f8ff28a-de74-446f-96ba-c6a2e8f70d92-000000/ZsB1btF0Wfkv46nj_duWhFFfiIg=170




Dick's and Jerry's scores were the same, so they are shown in ID order.

Solve above hackerrank problem with MySQL 
