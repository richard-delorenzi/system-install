#make deb
%.deb: %.equivs-control 
	equivs-build "$<"

#install one
.PHONY: %.install
%.install: %.deb
	sudo gdebi "$<"

#install all
src=$(wildcard *.equivs-control)
debs=$(src:%.equivs-control=%.deb)

.PHONY: install
install: $(debs)
	sudo gdebi $?
