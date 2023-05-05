project('raylib', 'c',
  license: 'Zlib'
)

add_project_arguments('-DPLATFORM_' + get_option('raylib_platform'),
  language: 'c'
)

glfw3_inc = include_directories('raylib/src/extrernal/glfw/src')

glfw3_src = [
  'raylib/src/extrernal/glfw/src/*.c'
]

glfw3_lib = static_library('raylib',
  glfw3_src,
  include_directories: raylib_inc
)

glfw_dep = glfw3_lib


raylib_src = [
  'raylib/src/raudio.c',
  'raylib/src/rcore.c',
  'raylib/src/rmodels.c',
  'raylib/src/rshapes.c',
  'raylib/src/rtext.c',
  'raylib/src/rtextures.c',
  'raylib/src/utils.c',
]

raylib_inc = include_directories('raylib/src')

raylib_lib = static_library('raylib',
  raylib_src,
  dependencies: glfw_dep,
  include_directories: raylib_inc
)

raylib_dep = declare_dependency(
  include_directories: raylib_inc,
  link_with: raylib_lib
)