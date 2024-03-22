project('gssdp-discover', 'c')
glib_version = '2.68'
glib = dependency('glib-2.0', version: '>= ' + glib_version)
gssdp = dependency('gssdp-1.6', version: '>= 1.6.0', default_options: ['sniffer=false'])
gobject = dependency('gobject-2.0', version: '>= ' + glib_version)

conf = configuration_data()
conf.set('VERSION', '"@0@"'.format(meson.project_version()))
conf.set('DATA_DIR', '"@0@"'.format(shareddir))
conf.set('HAVE_GTK_SOURCEVIEW', gtksourceview.found())
conf.set('GETTEXT_PACKAGE', '"@0@"'.format(meson.project_name()))
conf.set('LOCALEDIR', '"@0@"'.format(localedir))
cc = meson.get_compiler('c')
add_project_arguments(cc.get_supported_arguments('-Werror=deprecated-declarations'), language: 'c')
conf.set('GLIB_VERSION_MIN_REQUIRED', 'GLIB_VERSION_@0@'.format(glib_version.underscorify()))
conf.set('GLIB_VERSION_MAX_ALLOWED', 'GLIB_VERSION_@0@'.format(glib_version.underscorify()))

configure_file(input: 'config.h.meson', output: 'config.h', configuration: conf)
config_header = declare_dependency(include_directories : include_directories('.'))

executable('gssdp-discover', ['gssdp-discover.c'], dependencies : [gssdp, gobject], install: true)
