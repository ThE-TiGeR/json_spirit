SET(JSON_SPIRIT_SRCS
json_spirit_reader.cpp json_spirit_reader.h
json_spirit_value.cpp json_spirit_value.h
json_spirit_writer.cpp json_spirit_writer.h
json_spirit.h
json_spirit_error_position.h
json_spirit_reader_template.h
json_spirit_stream_reader.h
json_spirit_utils.h
json_spirit_writer_options.h
json_spirit_writer_template.h )
 
if (NOT Boost_INCLUDE_DIRS)
	find_package(Boost REQUIRED)
endif()

if (WIN32)
  set_source_files_properties(json_spirit_reader.cpp PROPERTIES COMPILE_FLAGS /bigobj)
endif()
INCLUDE_DIRECTORIES(${Boost_INCLUDE_DIRS})

ADD_LIBRARY(json_spirit STATIC ${JSON_SPIRIT_SRCS})

