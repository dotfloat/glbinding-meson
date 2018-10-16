configure_file(
  input : 'version.h.in',
  output : '@0@-version.h'.format(meta_project_name),
  configuration : conf_data,
  format : 'cmake@'
)

subdir('glbinding')
# subdir('glbinding-aux')

#if get_option('build-tools')
#   subdir('tools')
# endif

# if get_option('build-examples')
#   subdir('examples')
# endif

# if get_option('build-tests')
#   subdir('tests')
# endif
