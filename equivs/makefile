#default must be at top
default: my-packages_1.0_all.install
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

my-packages_1.0_all.equivs-control: packages.json
my-packages_1.0_all.equivs-control: equivs-control.template
my-packages_1.0_all.equivs-control:
	./create-equivs

################################################################
#all -- not used
src=$(wildcard ../equivs/*.equivs-control)
debs=$(src:../equivs/%.equivs-control=%.deb)


