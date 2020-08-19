set(EXE_TARGET_NAME example)

include_directories(include  ${Eigen_INCLUDE_DIRS})

set(${EXE_TARGET_NAME}_SRC
       apriltags_demo2.cpp
       Serial.cpp
)


add_executable(${EXE_TARGET_NAME} ${${EXE_TARGET_NAME}_SRC})

target_compile_features(${EXE_TARGET_NAME} PRIVATE cxx_std_11)

target_link_libraries(${EXE_TARGET_NAME} apriltags::apriltags v4l2 )

install(TARGETS ${EXE_TARGET_NAME} DESTINATION bin)

