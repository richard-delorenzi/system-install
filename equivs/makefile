
#make deb
%.deb: ../equivs/%.equivs-control 
	equivs-build "$<"

#install one
.PHONY: %.install
%.install: %.deb
	sudo gdebi "$<"

#install all
src=$(wildcard ../equivs/*.equivs-control)
debs=$(src:../equivs/%.equivs-control=%.deb)

.PHONY: install
install: $(debs)
	sudo gdebi $?

.PHONY: all
all: $(debs)
	%echo done
