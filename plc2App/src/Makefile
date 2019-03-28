TOP=../..

include $(TOP)/configure/CONFIG
#----------------------------------------
#  ADD MACRO DEFINITIONS AFTER THIS LINE
#=============================

#=============================
# Build the IOC application

PROD_IOC = plc2
# plc2.dbd will be created and installed
DBD += plc2.dbd

# plc2.dbd will be made up from these files:
plc2_DBD += base.dbd

# Include dbd files from all support applications:
#plc2_DBD += xxx.dbd
plc2_DBD += system.dbd
plc2_DBD += ether_ip.dbd
plc2_DBD += devIocStats.dbd
plc2_DBD += asSupport.dbd

# Add all the support libraries needed by this IOC
#plc2_LIBS += xxx
plc2_LIBS += ether_ip
plc2_LIBS += devIocStats
plc2_LIBS += autosave

# plc2_registerRecordDeviceDriver.cpp derives from plc2.dbd
plc2_SRCS += plc2_registerRecordDeviceDriver.cpp

# Build the main IOC entry point on workstation OSs.
plc2_SRCS_DEFAULT += plc2Main.cpp
plc2_SRCS_vxWorks += -nil-

# Add support from base/src/vxWorks if needed
#plc2_OBJS_vxWorks += $(EPICS_BASE_BIN)/vxComLibrary

# Finally link to the EPICS Base libraries
plc2_LIBS += $(EPICS_BASE_IOC_LIBS)

#===========================

include $(TOP)/configure/RULES
#----------------------------------------
#  ADD RULES AFTER THIS LINE
