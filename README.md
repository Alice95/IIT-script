
# Metoda 1: daca e nevoie sa afiseze si fisiere de tip imagine din dosare:
tree --du -h -P "*.jpg|*.png|*.jpeg|*.bmp" |
	sed 's/\[\(.*\)\]  \(.*\)/\2  \1/g'



# Metoda 2 : Daca nu este nevoie sa afisam fisiere de tip imagine din dosare:
tree --du -h -P "*.jpg|*.png|*.jpeg|*.bmp" |
	sed 's/\[\(.*\)\]  \(.*\)/\2  \1/g' | 
	grep -v "\.jpg" |
	grep -v "\.bmp" |
	grep -v "\.png" |
	grep -v "\.jpeg"
	
#Metoda 3
#!/bin/bash
sudo apt-get install tree
#You need to install the tree command.
ls -R -l | egrep '*.jpg$|*.jpeg$' | awk '{ x += $5 } END { print "total bytes of pictures:" x }'
tree $(pwd) -h -P '*.jpg|*.jpeg'

