project('gssdp-discover', 'c')
glib_version = '2.68'
glib = dependency('glib-2.0', version: '>= ' + glib_version)
gssdp = dependency('gssdp-1.6', version: '>= 1.6.0', default_options: ['sniffer=false'])
gobject = dependency('gobject-2.0', version: '>= ' + glib_version)

configure_file(input: 'config.h.meson', output: 'config.h', configuration: conf)
config_header = declare_dependency(include_directories : include_directories('.'))

executable('gssdp-discover', ['gssdp-discover.c'], dependencies : [gssdp, gobject], install: true)
