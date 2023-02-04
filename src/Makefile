PKG = ADMBP
PREFIX = $(shell pkg-config --variable=prefix gretl)

INP = $(PKG).inp $(PKG)_sample.inp
GFN = $(PKG).gfn

$(PKG).gfn : $(INP) $(PKG).spec
	gretlcli --makepkg $(PKG).inp

$(PKG).zip : $(INP) $(GFN)
	echo "makepkg $(PKG).zip" | gretlcli -b -

install: $(PKG).zip $(PKG).pdf
	echo "pkg install $(PKG).zip --local" | gretlcli -b -

# Only for zip-file
clean:
	rm -rf $(PKG).zip
	rm -rf session.inp
