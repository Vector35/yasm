project(re2c)

set(SOURCES
    main.c
    code.c
    dfa.c
    parser.c
    actions.c
    scanner.c
    mbo_getopt.c
    substr.c
    translate.c
    )

if(WIN32)
	set(NO_WARNINGS /w)
elseif(APPLE)
	set(NO_WARNINGS -Wno-everything)
else()
	set(NO_WARNINGS -w)
endif()

set_source_files_properties(${SOURCES} PROPERTIES COMPILE_FLAGS ${NO_WARNINGS})

add_executable(re2c ${SOURCES})
