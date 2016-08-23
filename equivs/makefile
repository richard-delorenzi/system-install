%.deb: %.equivs-control
	equivs-build "$<"

.PHONY: %.install
%.install: %.deb
	gdebi "$<"
