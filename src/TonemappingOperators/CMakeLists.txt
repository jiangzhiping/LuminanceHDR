#empty variables that will be filled in the subdirectories
SET(TM_LIBPFS_H )
SET(TM_LIBPFS_CPP )

ADD_SUBDIRECTORY(drago03)
ADD_SUBDIRECTORY(ashikhmin02)
ADD_SUBDIRECTORY(durand02)
ADD_SUBDIRECTORY(fattal02)
ADD_SUBDIRECTORY(ferradans11)
ADD_SUBDIRECTORY(mai11)
ADD_SUBDIRECTORY(mantiuk06)
ADD_SUBDIRECTORY(mantiuk08)
ADD_SUBDIRECTORY(pattanaik00)
ADD_SUBDIRECTORY(reinhard02)
ADD_SUBDIRECTORY(reinhard05)

# List all .h files in this directory
FILE(GLOB FILES_H *.h)
# List all .cpp files in this directory
FILE(GLOB FILES_CPP *.cpp)

ADD_LIBRARY(pfstmo ${TM_LIBPFS_H} ${TM_LIBPFS_CPP} ${FILES_H} ${FILES_CPP})
qt5_use_modules(pfstmo Core Gui Widgets)

SET(LUMINANCE_MODULES_GUI ${LUMINANCE_MODULES_GUI} pfstmo PARENT_SCOPE)
SET(LUMINANCE_MODULES_CLI ${LUMINANCE_MODULES_CLI} pfstmo PARENT_SCOPE)
