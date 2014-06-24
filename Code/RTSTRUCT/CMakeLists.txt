# This project is designed to export the contours to RTSTRUCT.
PROJECT(Export2RTSTRUCT)

# Find ITK Library
FIND_PACKAGE(ITK)
IF(ITK_FOUND)
  INCLUDE(${ITK_USE_FILE})
ELSE(ITK_FOUND)
  MESSAGE(FATAL_ERROR
          "Cannot build without ITK.  Please set ITK_DIR.")
ENDIF(ITK_FOUND)

ADD_EXECUTABLE(export2RTSTRUCT export2RTSTRUCT.cxx )

TARGET_LINK_LIBRARIES(export2RTSTRUCT ITKCommon ITKIO)
#=========================================================
#=========================================================
