SIM ?= icarus #simulator
TOPLEVEL_LANG ?= verilog
#declaring source files
VERILOG_SOURCES += $(PWD)/../hdl/or_gate.v 
VERILOG_SOURCES += $(PWD)/wrappers/or_test.v
VERILOG_SOURCES += $(PWD)/wrappers/ifc_test.v
VERILOG_SOURCES += $(PWD)/../hdl/ifc_or.v
VERILOG_SOURCES += $(PWD)/../hdl/FIFO1.v
VERILOG_SOURCES += $(PWD)/../hdl/FIFO2.v
#define make target
all: or ifc
or:
	rm -rf sim_build
	$(MAKE) sim MODULE=or_test TOPLEVEL=or_test #python module and verilog file
ifc:
	rm -rf sim_build
	$(MAKE) sim MODULE=ifc_test TOPLEVEL=ifc_test
coverage:
	rm -rf sim_build
	$(MAKE) sim MODULE=ifc_coverage TOPLEVEL=ifc_test
include $(shell cocotb-config --makefiles)/Makefile.sim #include cocotb Makefile and it is always declared at last
