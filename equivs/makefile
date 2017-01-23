%.deb: %.equivs-control 
	equivs-build "$<"

.PHONY: %.install
%.install: %.deb
	sudo gdebi "$<"
