project('raylib', 'c',
  license: 'Zlib'
)

add_project_arguments('-DPLATFORM_' + get_option('raylib_platform'),
  language: 'c'
)

glfw3_inc = include_directories('raylib/src/external/glfw/src')

glfw3_src = [
  'raylib/src/external/glfw/src/x11_window.c',
  'raylib/src/external/glfw/src/xkb_unicode.c',
  'raylib/src/external/glfw/src/x11_monitor.c',
  'raylib/src/external/glfw/src/wl_window.c',
  'raylib/src/external/glfw/src/x11_init.c',
  'raylib/src/external/glfw/src/wl_init.c',
  'raylib/src/external/glfw/src/wl_monitor.c',
  'raylib/src/external/glfw/src/win32_window.c',
  'raylib/src/external/glfw/src/window.c',
  'raylib/src/external/glfw/src/win32_thread.c',
  'raylib/src/external/glfw/src/win32_time.c',
  'raylib/src/external/glfw/src/win32_module.c',
  'raylib/src/external/glfw/src/win32_monitor.c',
  'raylib/src/external/glfw/src/wgl_context.c',
  'raylib/src/external/glfw/src/win32_init.c',
  'raylib/src/external/glfw/src/win32_joystick.c',
  'raylib/src/external/glfw/src/posix_time.c',
  'raylib/src/external/glfw/src/vulkan.c',
  'raylib/src/external/glfw/src/posix_poll.c',
  'raylib/src/external/glfw/src/posix_thread.c',
  'raylib/src/external/glfw/src/platform.c',
  'raylib/src/external/glfw/src/posix_module.c',
  'raylib/src/external/glfw/src/null_window.c',
  'raylib/src/external/glfw/src/osmesa_context.c',
  'raylib/src/external/glfw/src/null_init.c',
  'raylib/src/external/glfw/src/null_joystick.c',
  'raylib/src/external/glfw/src/null_monitor.c',
  'raylib/src/external/glfw/src/monitor.c',
  'raylib/src/external/glfw/src/linux_joystick.c',
  'raylib/src/external/glfw/src/init.c',
  'raylib/src/external/glfw/src/input.c',
  'raylib/src/external/glfw/src/egl_context.c',
  'raylib/src/external/glfw/src/glx_context.c',
  'raylib/src/external/glfw/src/context.c',
  'raylib/src/external/glfw/src/cocoa_time.c',
]

glfw3_lib = static_library('glfw3',
  glfw3_src,
  include_directories: glfw3_inc 
)

glfw_dep = declare_dependency(
  include_directories: glfw3_inc,
  link_with: glfw3_lib
)


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