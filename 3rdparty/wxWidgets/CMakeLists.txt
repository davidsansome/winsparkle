cmake_minimum_required(VERSION 2.6)

list(APPEND CMAKE_C_FLAGS -Wall)
list(APPEND CMAKE_CXX_FLAGS -Wall)

add_definitions(-DUNICODE -D_UNICODE)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)
include_directories(${CMAKE_CURRENT_BINARY_DIR}/include)

configure_file(${CMAKE_CURRENT_SOURCE_DIR}/include/wx/msw/setup.h
               ${CMAKE_CURRENT_BINARY_DIR}/include/wx/setup.h COPY_ONLY)

set(BASE_SOURCES
  src/common/any.cpp
  src/common/appbase.cpp
  src/common/arcall.cpp
  src/common/arcfind.cpp
  src/common/archive.cpp
  src/common/arrstr.cpp
  src/common/base64.cpp
  src/common/clntdata.cpp
  src/common/cmdline.cpp
  src/common/config.cpp
  src/common/convauto.cpp
  src/common/datetime.cpp
  src/common/datetimefmt.cpp
  src/common/datstrm.cpp
  src/common/dircmn.cpp
  src/common/dummy.cpp
  src/common/dynarray.cpp
  src/common/dynlib.cpp
  src/common/dynload.cpp
  src/common/encconv.cpp
  src/common/event.cpp
  src/common/evtloopcmn.cpp
  src/common/ffile.cpp
  src/common/file.cpp
  src/common/fileback.cpp
  src/common/fileconf.cpp
  src/common/filefn.cpp
  src/common/filename.cpp
  src/common/filesys.cpp
  src/common/filtall.cpp
  src/common/filtfind.cpp
  src/common/fmapbase.cpp
  src/common/fs_arc.cpp
  src/common/fs_filter.cpp
  src/common/fs_mem.cpp
  src/common/fswatchercmn.cpp
  src/common/hash.cpp
  src/common/hashmap.cpp
  src/common/init.cpp
  src/common/intl.cpp
  src/common/ipcbase.cpp
  src/common/list.cpp
  src/common/log.cpp
  src/common/longlong.cpp
  src/common/memory.cpp
  src/common/mimecmn.cpp
  src/common/module.cpp
  src/common/msgout.cpp
  src/common/mstream.cpp
  src/common/object.cpp
  src/common/platinfo.cpp
  src/common/powercmn.cpp
  src/common/process.cpp
  src/common/regex.cpp
  src/common/sstream.cpp
  src/common/stdpbase.cpp
  src/common/stdstream.cpp
  src/common/stopwatch.cpp
  src/common/strconv.cpp
  src/common/stream.cpp
  src/common/string.cpp
  src/common/stringimpl.cpp
  src/common/stringops.cpp
  src/common/strvararg.cpp
  src/common/sysopt.cpp
  src/common/tarstrm.cpp
  src/common/textbuf.cpp
  src/common/textfile.cpp
  src/common/timercmn.cpp
  src/common/timerimpl.cpp
  src/common/tokenzr.cpp
  src/common/txtstrm.cpp
  src/common/unichar.cpp
  src/common/uri.cpp
  src/common/ustring.cpp
  src/common/utilscmn.cpp
  src/common/variant.cpp
  src/common/wfstream.cpp
  src/common/wxcrt.cpp
  src/common/wxprintf.cpp
  src/common/xlocale.cpp
  src/common/xti.cpp
  src/common/xtistrm.cpp
  src/common/zipstrm.cpp
  src/common/zstream.cpp
  src/msw/basemsw.cpp
  src/msw/crashrpt.cpp
  src/msw/dde.cpp
  src/msw/debughlp.cpp
  src/msw/dir.cpp
  src/msw/dlmsw.cpp
  src/msw/evtloop.cpp
  src/msw/fswatcher.cpp
  src/msw/main.cpp
  src/msw/mimetype.cpp
  src/msw/mslu.cpp
  src/msw/power.cpp
  src/msw/regconf.cpp
  src/msw/registry.cpp
  src/msw/snglinst.cpp
  src/msw/stackwalk.cpp
  src/msw/stdpaths.cpp
  src/msw/thread.cpp
  src/msw/timer.cpp
  src/msw/utils.cpp
  src/msw/utilsexc.cpp
  src/msw/volume.cpp
  src/generic/fswatcherg.cpp
)

set(CORE_SOURCES
  src/common/accelcmn.cpp
  src/common/accesscmn.cpp
  src/common/anidecod.cpp
  src/common/appcmn.cpp
  src/common/artprov.cpp
  src/common/artstd.cpp
  src/common/bmpbase.cpp
  src/common/bookctrl.cpp
  src/common/btncmn.cpp
  src/common/cairo.cpp
  src/common/choiccmn.cpp
  src/common/clipcmn.cpp
  src/common/clrpickercmn.cpp
  src/common/cmdproc.cpp
  src/common/cmndata.cpp
  src/common/colourcmn.cpp
  src/common/combocmn.cpp
  src/common/containr.cpp
  src/common/cshelp.cpp
  src/common/ctrlcmn.cpp
  src/common/ctrlsub.cpp
  src/common/datacmn.cpp
  src/common/dcbase.cpp
  src/common/dcbufcmn.cpp
  src/common/dcgraph.cpp
  src/common/dcsvg.cpp
  src/common/dlgcmn.cpp
  src/common/dndcmn.cpp
  src/common/dobjcmn.cpp
  src/common/docmdi.cpp
  src/common/docview.cpp
  src/common/dpycmn.cpp
  src/common/dseldlg.cpp
  src/common/dummy.cpp
  src/common/effects.cpp
  src/common/event.cpp
  src/common/fddlgcmn.cpp
  src/common/filectrlcmn.cpp
  src/common/filepickercmn.cpp
  src/common/fldlgcmn.cpp
  src/common/fontcmn.cpp
  src/common/fontenumcmn.cpp
  src/common/fontmap.cpp
  src/common/fontpickercmn.cpp
  src/common/fontutilcmn.cpp
  src/common/framecmn.cpp
  src/common/fs_mem.cpp
  src/common/gaugecmn.cpp
  src/common/gbsizer.cpp
  src/common/gdicmn.cpp
  src/common/geometry.cpp
  src/common/gifdecod.cpp
  src/common/graphcmn.cpp
  src/common/headercolcmn.cpp
  src/common/headerctrlcmn.cpp
  src/common/helpbase.cpp
  src/common/iconbndl.cpp
  src/common/imagall.cpp
  src/common/imagbmp.cpp
  src/common/image.cpp
  src/common/imagfill.cpp
  src/common/imaggif.cpp
  src/common/imagiff.cpp
  src/common/imagjpeg.cpp
  src/common/imagpcx.cpp
  src/common/imagpng.cpp
  src/common/imagpnm.cpp
  src/common/imagtga.cpp
  src/common/imagtiff.cpp
  src/common/imagxpm.cpp
  src/common/layout.cpp
  src/common/lboxcmn.cpp
  src/common/listctrlcmn.cpp
  src/common/matrix.cpp
  src/common/menucmn.cpp
  src/common/mousemanager.cpp
  src/common/msgout.cpp
  src/common/nbkbase.cpp
  src/common/overlaycmn.cpp
  src/common/paper.cpp
  src/common/persist.cpp
  src/common/pickerbase.cpp
  src/common/popupcmn.cpp
  src/common/prntbase.cpp
  src/common/quantize.cpp
  src/common/radiocmn.cpp
  src/common/rearrangectrl.cpp
  src/common/rendcmn.cpp
  src/common/rgncmn.cpp
  src/common/settcmn.cpp
  src/common/sizer.cpp
  src/common/spinctrlcmn.cpp
  src/common/srchcmn.cpp
  src/common/statbar.cpp
  src/common/stattextcmn.cpp
  src/common/stockitem.cpp
  src/common/tbarbase.cpp
  src/common/textcmn.cpp
  src/common/textentrycmn.cpp
  src/common/toplvcmn.cpp
  src/common/treebase.cpp
  src/common/utilscmn.cpp
  src/common/valgen.cpp
  src/common/validate.cpp
  src/common/valtext.cpp
  src/common/wincmn.cpp
  src/common/windowid.cpp
  src/common/wrapsizer.cpp
  src/common/xpmdecod.cpp
  src/msw/accel.cpp
  src/msw/ole/access.cpp
  src/msw/ole/activex.cpp
  src/msw/app.cpp
  src/msw/artmsw.cpp
  src/msw/ole/automtn.cpp
  src/msw/bitmap.cpp
  src/msw/bmpbuttn.cpp
  src/msw/brush.cpp
  src/msw/button.cpp
  src/msw/caret.cpp
  src/msw/checkbox.cpp
  src/msw/checklst.cpp
  src/msw/choice.cpp
  src/msw/clipbrd.cpp
  src/msw/colordlg.cpp
  src/msw/colour.cpp
  src/msw/combo.cpp
  src/msw/combobox.cpp
  src/msw/control.cpp
  src/msw/cursor.cpp
  src/msw/data.cpp
  src/msw/ole/dataobj.cpp
  src/msw/dc.cpp
  src/msw/dcclient.cpp
  src/msw/dcmemory.cpp
  src/msw/dcprint.cpp
  src/msw/dcscreen.cpp
  src/msw/dialog.cpp
  src/msw/dialup.cpp
  src/msw/dib.cpp
  src/msw/dirdlg.cpp
  src/msw/display.cpp
  src/msw/dragimag.cpp
  src/msw/ole/dropsrc.cpp
  src/msw/ole/droptgt.cpp
  src/msw/enhmeta.cpp
  src/msw/evtloop.cpp
  src/msw/fdrepdlg.cpp
  src/msw/filedlg.cpp
  src/msw/font.cpp
  src/msw/fontdlg.cpp
  src/msw/fontenum.cpp
  src/msw/fontutil.cpp
  src/msw/frame.cpp
  src/msw/gauge.cpp
  src/msw/gdiimage.cpp
  src/msw/gdiobj.cpp
  src/msw/gdiplus.cpp
  src/msw/graphics.cpp
  src/msw/headerctrl.cpp
  src/msw/helpchm.cpp
  src/msw/helpwin.cpp
  src/msw/icon.cpp
  src/msw/imaglist.cpp
  src/msw/iniconf.cpp
  src/msw/listbox.cpp
  src/msw/listctrl.cpp
  src/msw/main.cpp
  src/msw/mdi.cpp
  src/msw/menu.cpp
  src/msw/menuitem.cpp
  src/msw/metafile.cpp
  src/msw/minifram.cpp
  src/msw/msgdlg.cpp
  src/msw/mslu.cpp
  src/msw/nativdlg.cpp
  src/msw/nativewin.cpp
  src/msw/notebook.cpp
  src/msw/ole/oleutils.cpp
  src/msw/ownerdrw.cpp
  src/msw/palette.cpp
  src/msw/pen.cpp
  src/msw/popupwin.cpp
  src/msw/printdlg.cpp
  src/msw/printwin.cpp
  src/msw/radiobox.cpp
  src/msw/radiobut.cpp
  src/msw/region.cpp
  src/msw/renderer.cpp
  src/msw/scrolbar.cpp
  src/msw/settings.cpp
  src/msw/slider.cpp
  src/msw/spinbutt.cpp
  src/msw/spinctrl.cpp
  src/msw/statbmp.cpp
  src/msw/statbox.cpp
  src/msw/statline.cpp
  src/msw/stattext.cpp
  src/msw/statusbar.cpp
  src/msw/textctrl.cpp
  src/msw/textentry.cpp
  src/msw/tglbtn.cpp
  src/msw/toolbar.cpp
  src/msw/tooltip.cpp
  src/msw/toplevel.cpp
  src/msw/treectrl.cpp
  src/msw/utilsgui.cpp
  src/msw/ole/uuid.cpp
  src/msw/uxtheme.cpp
  src/msw/volume.cpp
  src/msw/window.cpp
  src/generic/busyinfo.cpp
  src/generic/buttonbar.cpp
  src/generic/choicbkg.cpp
  src/generic/choicdgg.cpp
  src/generic/clrpickerg.cpp
  src/generic/collpaneg.cpp
  src/generic/combog.cpp
  src/generic/dcpsg.cpp
  src/generic/dirctrlg.cpp
  src/generic/dragimgg.cpp
  src/generic/filectrlg.cpp
  src/generic/filepickerg.cpp
  src/generic/fontpickerg.cpp
  src/generic/graphicc.cpp
  src/generic/headerctrlg.cpp
  src/generic/listbkg.cpp
  src/generic/logg.cpp
  src/generic/numdlgg.cpp
  src/generic/panelg.cpp
  src/generic/printps.cpp
  src/generic/prntdlgg.cpp
  src/generic/progdlgg.cpp
  src/generic/renderg.cpp
  src/generic/scrlwing.cpp
  src/generic/selstore.cpp
  src/generic/spinctlg.cpp
  src/generic/splitter.cpp
  src/generic/srchctlg.cpp
  src/generic/statbmpg.cpp
  src/generic/stattextg.cpp
  src/generic/statusbr.cpp
  src/generic/textdlgg.cpp
  src/generic/tipwin.cpp
  src/generic/toolbkg.cpp
  src/generic/treebkg.cpp
  src/generic/treectlg.cpp
  src/generic/vlbox.cpp
  src/generic/vscroll.cpp
)

add_library(wxWidgets STATIC
  ${BASE_SOURCES}
  ${CORE_SOURCES}
)

target_link_libraries(wxWidgets
  comctl32
)
