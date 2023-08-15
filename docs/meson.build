doxygen = find_program('doxygen', required : false)
if not doxygen.found()
    error('Skipping docs due to missing Doxygen')
    subdir_done()
endif

subdir('doxygen')
