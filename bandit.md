Login:


lvl 1- ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If

special symbol -

can be read using ./
ie. cat ./-

lvl 2- 263JGJPfgU6LtdEvgfWU1XP5yac29fFx

having spaces
--spaces in this filename--
if it was just
spaces in this filename
then
cat spaces\ in\ this\ filename will do the job
since we got --
we need to use ./
By prefixing with ./, you explicitly tell the shell: “This is a file in the current directory.”
cat ./--spaces\ in\ this\ filename--

lvl 3- MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx

stored in inhere directory
cd inhere
files are hidden
used ls -a
saw ...Hiding-From-You
cat ...Hiding-From-You

lvl 4- 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ

file is in human readable form
we can cat every file but it is time consuming so
used bash script
for i in $(ls); do file ./$i; done
hence found that -file07 has the password

lvl 5- 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw

hints size 1033 bytes human readable
we can do it manually by using recursive listing
that is ls -R or ls -alR(gives all details of directories and files inside it)

used
find . -readable -size 1033c ! -executable
. stands for current directory
c stands for bytes

lvl 6- HWasnPhtq9AVKe0dmk45nxy20cvUa6EG

owned by user bandit7
owned by group bandit6
size id 33 bytes

used
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null

/var/lib/dpkg/info/bandit7.password

cat /var/lib/dpkg/info/bandit7.password

lvl 7- morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj

password in data.text next to the word millionth
used
wc -l data.txt
found out that it has more than 9k+ words

cat data.txt | grep "millionth"

grep will take the output of the cat data.text and find the word millionth

millionth dfwvzFQi4mU0wfNbFOe9RoWskMLg7eE

lvl 8-dfwvzFQi4mU0wfNbFOe9RoWskMLg7eE


