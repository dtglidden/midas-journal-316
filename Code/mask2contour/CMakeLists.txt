# This project is designed to convert the masks to contours.
PROJECT(Mask2Contour)

# Find ITK Library
FIND_PACKAGE(ITK)
IF(ITK_FOUND)
  INCLUDE(${ITK_USE_FILE})
ELSE(ITK_FOUND)
  MESSAGE(FATAL_ERROR
          "Cannot build without ITK.  Please set ITK_DIR.")
ENDIF(ITK_FOUND)

ADD_EXECUTABLE(mask2contour mask2contour.cxx)

TARGET_LINK_LIBRARIES(mask2contour ITKCommon ITKIO ITKIOReview)
# If older versions of ITK are used, ITKIOReview may have to be replaced
#  with ITKReview.
#=========================================================
#=========================================================
