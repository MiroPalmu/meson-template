###############################
# Set up Doxygen
###############################

doxygen = find_program('doxygen', required : false)
if not doxygen.found()
    error('Skipping docs due to missing Doxygen')
    subdir_done()
endif

# Definfe variables used in Doxyfile.in
doxygen_config_data = configuration_data({
    'NAME' : meson.project_name(),
    'VERSION' : meson.project_version(),
    # In Doxygen.in:
    #   INPUT = "@INPUT@"
    # so we just have to seperate sources with ' '
    'INPUT' : '" "'.join([
        meson.project_source_root() + '/src',
        meson.project_source_root() + '/include'
    ]),
    'OUTPUT_DIRECTORY' : meson.current_build_dir()
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
    command: [doxygen, '@INPUT@'],
    install: false
)
