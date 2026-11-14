# okaru-view: image viewer de OKARU. Se compila contra el núcleo instalado (paquete okaru-core).
project('okaru-view', 'cpp',
  version: files('VERSION'),
  meson_version: '>=1.1',
  default_options: ['cpp_std=c++23', 'cpp_extensions=false', 'warning_level=0', 'b_ndebug=if-release'],
)

# El núcleo y sus bibliotecas son privados (/usr/lib/okaru): se enlazan con su ruta en el binario.
_okaru_libdir = get_option('prefix') / get_option('libdir') / 'okaru'
_deps = [dependency('okaru-core'), dependency('exiv2'), dependency('gdk-pixbuf-2.0'), dependency('libraw'), dependency('libturbojpeg')]
_inc = include_directories('src')
_args = ['-Wall', '-Wextra', '-Wno-missing-field-initializers', '-Wpedantic', '-Wconversion', '-Wshadow']

executable('okaru-view',
  sources: files('src/apps/viewer/main.cpp', 'src/apps/viewer/viewer_image.cpp', 'src/apps/viewer/viewer_window.cpp'),
  include_directories: _inc,
  dependencies: _deps,
  cpp_args: _args,
  install_rpath: _okaru_libdir,
  install: true,
)

# Sus textos, que el núcleo busca en /usr/share/okaru/apps/viewer/translations.
install_subdir('apps/viewer/translations', install_dir: get_option('datadir') / 'okaru' / 'apps' / 'viewer')
install_data('assets/dev.okaru.Viewer.desktop', install_dir: get_option('datadir') / 'applications')

if get_option('tests').allowed()
  test('okaru_viewer_image', executable('okaru_viewer_image_test',
    sources: files('tests/okaru_viewer_image_test.cpp', 'src/apps/viewer/viewer_image.cpp'),
    include_directories: _inc,
    dependencies: _deps,
    build_rpath: _okaru_libdir,
    override_options: ['b_ndebug=false'],
  ))
endif
