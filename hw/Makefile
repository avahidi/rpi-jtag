
NAME = gfg

all:
	echo clean, oshpark, dirtypcbs

oshpark:
	rm -rf grebers/oshpark
	mkdir grebers/oshpark

	cp grebers/*.gtl grebers/*.gts grebers/*.gto grebers/*.gbl \
	grebers/*.gbs grebers/*.gbo grebers/*.drl grebers/*.gm1 grebers/oshpark

	rm -f grebers/oshpark.zip
	cd grebers && zip oshpark.zip oshpark

	ls -l grebers/oshpark*
	gerbv grebers/oshpark/*


dirtypcbs:
	rm -rf grebers/dirtypcbs
	mkdir grebers/dirtypcbs

	cp grebers/*.gtl grebers/dirtypcbs/$(NAME).GTL
	cp grebers/*.gts grebers/dirtypcbs/$(NAME).GTS
	cp grebers/*.gto grebers/dirtypcbs/$(NAME).GTO

	cp grebers/*.gbl grebers/dirtypcbs/$(NAME).GBL
	cp grebers/*.gbs grebers/dirtypcbs/$(NAME).GBS
	cp grebers/*.gbo grebers/dirtypcbs/$(NAME).GBO
	cp grebers/*.drl grebers/dirtypcbs/$(NAME).TXT
	cp grebers/*.gm1 grebers/dirtypcbs/$(NAME).GKO
	rm -f grebers/dirtypcbs.zip
	cd grebers && zip dirtypcbs.zip dirtypcbs
	ls -l grebers/dirtypcbs*
	gerbv grebers/dirtypcbs/*


view:
	gerbview grebers/*

clean:
	rm -rf grebers
