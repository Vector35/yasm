project(genperf)

set(SOURCES
    genperf.c
    perfect.c
    ../../libyasm/phash.c
    ../../libyasm/xmalloc.c
    ../../libyasm/xstrdup.c
    )

if(WIN32)
	set(NO_WARNINGS /w)
elseif(APPLE)
	set(NO_WARNINGS -Wno-everything)
else()
	set(NO_WARNINGS -w)
endif()

set_source_files_properties(${SOURCES} PROPERTIES COMPILE_FLAGS ${NO_WARNINGS})

add_executable(genperf ${SOURCES})
set_target_properties(genperf PROPERTIES COMPILE_FLAGS -DYASM_LIB_DECL=)
