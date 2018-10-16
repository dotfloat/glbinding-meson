project('glbinding', 'cpp', version : '3.0.2', default_options : ['cpp_std=c++11'])

meta_project_name        = 'glbinding'
meta_project_description = 'A C++ binding for the OpenGL API, generated using the gl.xml specification.'
meta_author_organization = 'CG Internals GmbH'
meta_author_domain       = 'https://github.com/cginternals/glbinding/'
meta_author_maintainer   = 'opensource@cginternals.com'
meta_version_major       = '3'
meta_version_minor       = '0'
meta_version_patch       = '2'
meta_version_revision    = 'N/A'
meta_version             = '@0@.@1@.@2@'.format(meta_version_major, meta_version_minor, meta_version_patch)
meta_name_version        = '@0@ v@1@ (@2@)'.format(meta_project_name, meta_version, meta_version_revision)

conf_data = configuration_data()
conf_data.set('META_PROJECT_NAME',        meta_project_name)
conf_data.set('META_PROJECT_DESCRIPTION', meta_project_description)
conf_data.set('META_AUTHOR_ORGANIZATION', meta_author_organization)
conf_data.set('META_AUTHOR_DOMAIN',       meta_author_domain)
conf_data.set('META_AUTHOR_MAINTAINER',   meta_author_maintainer)
conf_data.set('META_VERSION_MAJOR',       meta_version_major)
conf_data.set('META_VERSION_MINOR',       meta_version_minor)
conf_data.set('META_VERSION_PATCH',       meta_version_patch)
conf_data.set('META_VERSION_REVISION',    meta_version_revision)
conf_data.set('META_VERSION',             meta_version)
conf_data.set('META_NAME_VERSION',        meta_name_version)

subdir('source')
