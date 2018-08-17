jpeg_sources = [
  'gstjpeg.c',
  'gstjpegenc.c',
  'gstjpegdec.c',
]

jpeglib_dep = dependency('jpeg',
  required : get_option('jpeg'),
  fallback : ['libjpeg', 'jpeg_dep'],
)

if jpeglib_dep.found()
  gstjpeg = library('gstjpeg',
    jpeg_sources,
    c_args : gst_plugins_good_args,
    link_args : noseh_link_args,
    include_directories : [configinc, libsinc],
    dependencies : [gst_dep, gstbase_dep, gstvideo_dep, jpeglib_dep, libm],
    install : true,
    install_dir : plugins_install_dir,
  )
  pkgconfig.generate(gstjpeg, install_dir : plugins_pkgconfig_install_dir)
endif
