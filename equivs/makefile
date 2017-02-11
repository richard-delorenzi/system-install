#default must be at top
default: all
	@echo "%done default"

#make deb
%.deb: ../equivs/%.equivs-control
	@echo %making "$@" from "$<"
	equivs-build "$<"

#install one
.PHONY: %.install
%.install: %.deb
	@echo %installing "$<"
	sudo gdebi "$<"

#all
src=$(wildcard ../equivs/*.equivs-control)
debs=$(src:../equivs/%.equivs-control=%.deb)

#install all
.PHONY: install
install: $(debs)
	@echo "%installing all"
	sudo gdebi $?

#build all
.PHONY: all
all: $(debs)
	@echo "%done all"
