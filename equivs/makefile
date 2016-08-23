%.deb: %.equivs-control 
	equivs-build "$<" #names do not match

.PHONY: %.install
%.install: %.deb
	sudo gdebi "$<"
