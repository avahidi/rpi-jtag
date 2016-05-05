
NAME = rpi2_jtag

all:
	echo edit, view clean, oshpark, dirtypcbs

#

edit: gerbers
	kicad rpi2_jtag.pro

view:
	gerbview gerbers/*

#

check:
ifneq (,$(wildcard gerbers/*NPTH.drl))
	@echo "You should have combined PTH and NPTH drils into one file"
	@echo "Remove the gerbers folder and restart"
	@exit 20
endif

oshpark: check
	rm -rf gerbers/oshpark
	mkdir gerbers/oshpark

	cp gerbers/*.gtl gerbers/*.gts gerbers/*.gto gerbers/*.gbl \
	gerbers/*.gbs gerbers/*.gbo gerbers/*.drl gerbers/*.gm1 gerbers/oshpark

	rm -f ../data/gerbers/oshpark.zip
	cd gerbers && zip ../../data/oshpark.zip oshpark/*

	ls -l gerbers/oshpark*
	gerbv gerbers/oshpark/*


dirtypcbs: check
	rm -rf gerbers/dirtypcbs
	mkdir gerbers/dirtypcbs

	cp gerbers/*.gtl gerbers/dirtypcbs/$(NAME).GTL
	cp gerbers/*.gts gerbers/dirtypcbs/$(NAME).GTS
	cp gerbers/*.gto gerbers/dirtypcbs/$(NAME).GTO

	cp gerbers/*.gbl gerbers/dirtypcbs/$(NAME).GBL
	cp gerbers/*.gbs gerbers/dirtypcbs/$(NAME).GBS
	cp gerbers/*.gbo gerbers/dirtypcbs/$(NAME).GBO
	cp gerbers/*.drl gerbers/dirtypcbs/$(NAME).TXT
	cp gerbers/*.gm1 gerbers/dirtypcbs/$(NAME).GKO
	rm -f ../data/gerbers/dirtypcbs.zip
	cd gerbers && zip ../../data/dirtypcbs.zip dirtypcbs/*
	ls -l gerbers/dirtypcbs*
	gerbv gerbers/dirtypcbs/*

#

clean:
	rm -rf gerbers


gerbers:
	mkdir gerbers
