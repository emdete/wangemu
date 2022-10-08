# wx-config to use, may be overridden on make command line.
WX_CONFIG := wx-config
WX_CXXFLAGS := $(shell $(WX_CONFIG) --cxxflags) -g -D_DEBUG
WX_LIBS := $(shell $(WX_CONFIG) --libs) -g
OBJECTS := \
	CardInfo.o \
	Cpu2200t.o \
	Cpu2200vp.o \
	DiskCtrlCfgState.o \
	IoCard.o \
	IoCardDisk.o \
	IoCardDisk_Controller.o \
	IoCardDisplay.o \
	IoCardKeyboard.o \
	IoCardPrinter.o \
	IoCardTermMux.o \
	Scheduler.o \
	ScriptFile.o \
	SysCfgState.o \
	TermMuxCfgState.o \
	Terminal.o \
	UiCrt.o \
	UiCrtConfigDlg.o \
	UiCrtErrorDlg.o \
	UiCrtFrame.o \
	UiCrtStatusBar.o \
	UiCrt_Charset.o \
	UiCrt_Keyboard.o \
	UiCrt_Render.o \
	UiDiskCtrlCfgDlg.o \
	UiDiskFactory.o \
	UiMyAboutDlg.o \
	UiMyStaticText.o \
	UiPrinter.o \
	UiPrinterConfigDlg.o \
	UiPrinterFrame.o \
	UiSystem.o \
	UiSystemConfigDlg.o \
	UiTermMuxCfgDlg.o \
	Wvd.o \
	dasm.o \
	dasm_vp.o \
	error_table.o \
	host.o \
	i8080.o \
	i8080_dasm.o \
	system2200.o \
	ucode_2200B.o \
	ucode_2200T.o \
	ucode_boot_vp.o

.cpp.o:
	$(CXX) -c -o $@ $(WX_CXXFLAGS) $(CXXFLAGS) $<

../wangemu: $(OBJECTS)
	$(CXX) -o $@ $(OBJECTS) $(LDFLAGS) $(WX_LIBS) $(LIBS)

run: ../wangemu
	(cd .. && ./wangemu)

dbg: ../wangemu
	ddd ../wangemu

clean:
	rm -f *.o ../wangemu
