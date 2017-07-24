#default must be at top
default: my-packages_1.0_all.install
	@echo "%done default"

#don't delete stuff that we make
.SECONDARY:

#make deb
%.deb: %.equivs-control
	@echo %making "$@" from "$<"
	equivs-build "$<"

#install one
.PHONY: %.install
%.install: %.deb
	@echo %installing "$<"
	sudo gdebi "$<"

#
my-packages_1.0_all.equivs-control: packages.json
my-packages_1.0_all.equivs-control: equivs-control.template
my-packages_1.0_all.equivs-control:
	@echo %making "$@"
	./create-equivs
	echo ${debs}

################################################################
#all -- not used
src=$(wildcard *.equivs-control)
debs=$(src:%.equivs-control=%.deb)


