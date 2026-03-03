project('imgui', 'cpp', version: '1.91.8')

imgui_files = files(
  'imgui.cpp',
  'imgui_demo.cpp',
  'imgui_draw.cpp',
  'imgui_tables.cpp',
  'imgui_widgets.cpp',
  'backends/imgui_impl_vulkan.cpp',
  'backends/imgui_impl_win32.cpp'
)

imgui_inc = declare_dependency(include_directories: include_directories('.', 'backends'))

imgui_inc_dirs = include_directories('.', 'backends')


vulkan_dep = dependency('vulkan', required: false)

imgui_lib = static_library('imgui',
  imgui_files,
  include_directories : imgui_inc_dirs,
  dependencies        : [vulkan_dep],
  cpp_args            : ['-DIMGUI_USER_CONFIG="imconfig.h"'],
  override_options    : ['cpp_std=c++17']
)

imgui_dep = declare_dependency(
  link_with           : imgui_lib,
  include_directories : imgui_inc_dirs
)
