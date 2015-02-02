src_dir:=src
hdpi_dir:=res/drawable-hdpi
ldpi_dir:=res/drawable-ldpi
mdpi_dir:=res/drawable-mdpi

names:=$(patsubst $(src_dir)/%,%,$(wildcard $(src_dir)/*.png $(src_dir)/*.jpg))
hdpi_target:=$(patsubst %,$(hdpi_dir)/%,$(names))
ldpi_target:=$(patsubst %,$(ldpi_dir)/%,$(names))
mdpi_target:=$(patsubst %,$(mdpi_dir)/%,$(names))

appicon:=googleplay/appicon.png
feature:=googleplay/feature.png
canvas:=googleplay/canvas.png
work:=googleplay/work.png

default: all

hdpi: $(hdpi_dir) $(hdpi_target)

ldpi: $(ldpi_dir) $(ldpi_target)

mdpi: $(mdpi_dir) $(mdpi_target)

googleplay: $(appicon) $(feature)

all: hdpi ldpi mdpi googleplay

clean: 
	rm $(hdpi_target) $(ldpi_target) $(mdpi_target) $(appicon) $(feature)

$(hdpi_dir):
	@mkdir -p $@

$(ldpi_dir):
	@mkdir -p $@

$(mdpi_dir):
	@mkdir -p $@

$(hdpi_dir)/tab_%.png: $(src_dir)/tab_%.png
	convert -geometry 48x $< $@
	identify $@

$(ldpi_dir)/tab_%.png: $(src_dir)/tab_%.png
	convert -geometry 32x $< $@
	identify $@

$(mdpi_dir)/tab_%.png: $(src_dir)/tab_%.png
	convert -geometry 40x $< $@
	identify $@

$(hdpi_dir)/menu_%.png: $(src_dir)/menu_%.png
	convert -geometry 72x $< $@
	identify $@

$(ldpi_dir)/menu_%.png: $(src_dir)/menu_%.png
	convert -geometry 36x $< $@
	identify $@

$(mdpi_dir)/menu_%.png: $(src_dir)/menu_%.png
	convert -geometry 48x $< $@
	identify $@

$(hdpi_dir)/btn_%.png: $(src_dir)/btn_%.png
	convert -geometry 48x $< $@
	identify $@

$(ldpi_dir)/btn_%.png: $(src_dir)/btn_%.png
	convert -geometry 24x $< $@
	identify $@

$(mdpi_dir)/btn_%.png: $(src_dir)/btn_%.png
	convert -geometry 36x $< $@
	identify $@

$(hdpi_dir)/headerbtn_%.png: $(src_dir)/headerbtn_%.png
	convert -geometry 36x $< $@
	identify $@

$(ldpi_dir)/headerbtn_%.png: $(src_dir)/headerbtn_%.png
	convert -geometry 18x $< $@
	identify $@

$(mdpi_dir)/headerbtn_%.png: $(src_dir)/headerbtn_%.png
	convert -geometry 24x $< $@
	identify $@

$(hdpi_dir)/tagbtn_%.png: $(src_dir)/tagbtn_%.png
	convert -geometry 24x $< $@
	identify $@

$(ldpi_dir)/tagbtn_%.png: $(src_dir)/tagbtn_%.png
	convert -geometry 12x $< $@
	identify $@

$(mdpi_dir)/tagbtn_%.png: $(src_dir)/tagbtn_%.png
	convert -geometry 18x $< $@
	identify $@

$(hdpi_dir)/launcher_%.png: $(src_dir)/launcher_%.png
	convert -geometry 72x $< $@
	identify $@

$(ldpi_dir)/launcher_%.png: $(src_dir)/launcher_%.png
	convert -geometry 36x $< $@
	identify $@

$(mdpi_dir)/launcher_%.png: $(src_dir)/launcher_%.png
	convert -geometry 48x $< $@
	identify $@

$(hdpi_dir)/bullet_%.png: $(src_dir)/bullet_%.png
	convert -geometry 50x $< $@
	identify $@

$(ldpi_dir)/bullet_%.png: $(src_dir)/bullet_%.png
	convert -geometry 50x $< $@
	identify $@

$(mdpi_dir)/bullet_%.png: $(src_dir)/bullet_%.png
	convert -geometry 50x $< $@
	identify $@

$(appicon): $(src_dir)/launcher_main.png
	@mkdir -p $(@D)
	convert -geometry 512x $< $@
	identify $@

$(feature): $(src_dir)/launcher_main.png
	@mkdir -p $(@D)
	convert -size 1024x500 xc:transparent $(canvas)
	convert -geometry 1024x500 $< $(work)
	convert -composite $(canvas) $(work) -gravity west $@
	identify $@

