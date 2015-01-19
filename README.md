
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
