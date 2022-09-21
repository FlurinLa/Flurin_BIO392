# code to read .pgxseg file
Flurin Läuchli

```
import pandas as pd

file = open("data.pgxseg", newline="")

lines = file.readlines()

for line in lines:
    if "#" not in line:
        with open("data.csv", "a+") as f:
            f.write(line)

df = pd.read_csv("data.csv")


```

>This code is an adapted version of the code presented in the lecture, as my program did not work at all.
