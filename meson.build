project('gssdp-discover', 'c')
gssdp = dependency('gssdp-1.2', version: '>= 1.2.0', default_options: ['sniffer=false'])
gobject = dependency('gobject-2.0', version: '>= 2.24')

executable('gssdp-discover', ['gssdp-discover.c'], dependencies : [gssdp, gobject], install: true)
