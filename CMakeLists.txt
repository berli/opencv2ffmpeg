
cmake_minimum_required(VERSION 3.0)

set(CMAKE_CXX_STANDARD 11)
set(EXE OpenCV2FFmpeg)

find_package(OpenCV)
if (NOT OpenCV_FOUND)
	message(WARNING "OpenCV not found. Test will not be built.")
else()
	    include_directories(${OpenCV_INCLUDE_DIRS})
		# list(APPEND _required_libs ${OpenCV_LIBS})
	   # 
	      # add_executable(facedet_test src/test/facedetection_test.cpp)
		     # target_link_libraries(facedet_test ${facedet_required_libs})
endif()

add_executable(${EXE} main.cpp)
target_link_libraries(${EXE} ${OpenCV_LIBS} swscale avutil avcodec avformat)

