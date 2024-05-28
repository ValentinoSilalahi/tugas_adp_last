from termcolor import colored, cprint

br = "blue"
wt = "white"
yw = "yellow"

vs = [
    " -   -  ---   ---       -   ",
    " -   -   -   -         - -  ",
    " -   -   -    -       -   - ",
    " -   -   -     -     ------- ",
    "  - -    -      -   -       - ",
    "   -    ---  ---   -         -  "
]

baris = 5  
kolom = 8                   


wtr = 15 // 2
brr = (15 - wtr) // 2
ywr = 15 - wtr - brr

ltr = [["" for _ in range(45)] for _ in range(15)]

for i in range(15):
    for j in range(45):
        if i < brr:
            ltr[i][j] = br
        elif i < brr + wtr:
            ltr[i][j] = wt
        else:
            ltr[i][j] = yw

for i in range(len(vs)):
    for j in range(len(vs[i])):
        if vs[i][j] != ' ':
            bts = baris + i
            jr = kolom + j
            if brr <= bts < brr + wtr:  
                ltr [bts][jr] = br

for i in range(15):
    for j in range(45):
        cprint(" ", ltr[i][j], "on_" + ltr[i][j], end="")
    print()
