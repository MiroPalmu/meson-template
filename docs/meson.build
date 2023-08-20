doxygen = find_program('doxygen', required : false)
if not doxygen.found()
    error('Skipping docs due to missing Doxygen')
    subdir_done()
endif

subdir('doxygen')


sphinx = find_program('sphinx-build', required: false)
if not sphinx.found()
    error('Skipping docs due to missing Sphinx')
    subdir_done()
endif

subdir('sphinx')
