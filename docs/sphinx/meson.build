doxygen = find_program('doxygen', required : false)
if not doxygen.found()
    error('Skipping docs due to missing Doxygen')
    subdir_done()
endif

<<<<<<< Updated upstream
subdir('doxygen')
=======
# Definfe variables used in Doxyfile.in
doxygen_config_data = configuration_data({
    'NAME' : meson.project_name(),
    'VERSION' : meson.project_version(),
    'SOURCE_ROOT' : meson.project_source_root(),
    'BUILD_ROOT' : meson.project_build_root()
})

if find_program('dot', required : false).found()
    doxygen_config_data.set('HAVE_DOT', 'YES')
else
    doxygen_config_data.set('HAVE_DOT', 'NO')
endif

doxyfile = configure_file(
    input: 'Doxyfile.in',
    output: 'Doxyfile',
    configuration: doxygen_config_data,
    install: false
)


html_target = custom_target(
    'docs_target',
    input: doxyfile,
    output: 'html',
    command: [doxygen, doxyfile],
    install: false
)


###############################
# Set up Sphinx
###############################

sphinx = find_program('sphinx
>>>>>>> Stashed changes
