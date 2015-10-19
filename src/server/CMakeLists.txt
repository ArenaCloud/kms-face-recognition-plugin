cmake_minimum_required (VERSION 2.8)

include (CodeGenerator)

set (FACE_RECOGNITION_IMPL_EXTRA_HEADERS
  ${CMAKE_CURRENT_SOURCE_DIR}/implementation/objects/face_rec/face_training.h
  ${CMAKE_CURRENT_SOURCE_DIR}/implementation/objects/face_rec/face_recognition.h
)
set (FACE_RECOGNITION_IMPL_EXTRA_SOURCES
  ${CMAKE_CURRENT_SOURCE_DIR}/implementation/objects/face_rec/face_training.cpp
  ${CMAKE_CURRENT_SOURCE_DIR}/implementation/objects/face_rec/face_recognition.cpp
)

generate_code (
  MODELS ${CMAKE_CURRENT_SOURCE_DIR}/interface
  SERVER_STUB_DESTINATION ${CMAKE_CURRENT_SOURCE_DIR}/implementation/objects
  SERVER_IMPL_LIB_EXTRA_SOURCES ${FACE_RECOGNITION_IMPL_EXTRA_SOURCES}
  SERVER_IMPL_LIB_EXTRA_HEADERS ${FACE_RECOGNITION_IMPL_EXTRA_HEADERS}
)