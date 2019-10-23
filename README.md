
import re

n = int(input())
inputs = list()
for _  in range(n):
    inputs.append(input())

for inp in inputs:
    valid = re.findall("[4-6][0-9][0-9][0-9][-]*[0-9][0-9][0-9][0-9][-]*[0-9][0-9][0-9][0-9][-]*[0-9][0-9][0-9][0-9]",inp)
    if valid == [] or len(inp) > 19:
        print("Invalid")
    else:
        temp_valid = ''.join(valid[0].split('-'))
        valid = re.findall(r"(\d)\1{3}",temp_valid)
        if valid:
            print("Invalid")
        else:
            print("Valid")
