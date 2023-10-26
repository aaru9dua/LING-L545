all: hindi.gen.hfst

grn.lexc.hfst: hindi.lexc
	hfst-lexc hindi.lexc -o hindi.lexc.hfst

grn.twol.hfst: grn.twol
	hfst-twolc hindi.twol -o hindi.twol.hfst
        
grn.gen.hfst: hindi.lexc.hfst hindi.twol.hfst
	hfst-compose-intersect -1 hindi.lexc.hfst -2 hindi.twol.hfst -o hindi.gen.hfst