additional_dep = []

if get_option('build-with-boost-thread')
  boost_dep = dependency('boost', modules : ['thread'], required : false)
  if boost_dep.found()
    message('Use Boost for thread.')
    additional_dep += boost_dep
  else
    warning('build-with-boost-thread is set to true: Boost not found.')
    warning('Defaulting to C++11 thread.')
  endif
endif

# Target name
target = 'glbinding'

message('Lib @0@'.format(target))

#
# Sources
#

include_path = join_paths('include', target)
source_path = 'source'

libglbinding_hdr = files(
  join_paths(include_path, 'nogl.h'),

  join_paths(include_path, 'gl', 'bitfield.h'),
  join_paths(include_path, 'gl', 'boolean.h'),
  join_paths(include_path, 'gl', 'enum.h'),
  join_paths(include_path, 'gl', 'extension.h'),
  join_paths(include_path, 'gl', 'functions.h'),
  join_paths(include_path, 'gl', 'types.h'),
  join_paths(include_path, 'gl', 'values.h'),

  join_paths(include_path, 'glbinding.h'),
  join_paths(include_path, 'AbstractFunction.h'),
  join_paths(include_path, 'CallbackMask.h'),
  join_paths(include_path, 'Function.h'),
  join_paths(include_path, 'FunctionCall.h'),
  join_paths(include_path, 'Binding.h'),
  join_paths(include_path, 'ProcAddress.h'),
  join_paths(include_path, 'Value.h'),
  join_paths(include_path, 'Version.h'),
  join_paths(include_path, 'Version.inl'),
  join_paths(include_path, 'SharedBitfield.h'),

  # KHR binding
  join_paths(include_path, 'AbstractFunction.h'),
  join_paths(include_path, 'AbstractState.h'),
  join_paths(include_path, 'AbstractValue.h'),
  join_paths(include_path, 'Boolean8.h'),
  join_paths(include_path, 'Boolean8.inl'),
  join_paths(include_path, 'CallbackMask.h'),
  join_paths(include_path, 'CallbackMask.inl'),
  join_paths(include_path, 'ContextHandle.h'),
  join_paths(include_path, 'Function.h'),
  join_paths(include_path, 'Function.inl'),
  join_paths(include_path, 'FunctionCall.h'),
  join_paths(include_path, 'ProcAddress.h'),
  join_paths(include_path, 'SharedBitfield.h'),
  join_paths(include_path, 'SharedBitfield.inl'),
  join_paths(include_path, 'State.h'),
  join_paths(include_path, 'Value.h'),
  join_paths(include_path, 'Value.inl'),
  join_paths(include_path, 'Version.h'),
  join_paths(include_path, 'Version.inl')
)

libglbinding_src = files(
  join_paths(source_path, 'glbinding.cpp'),
  join_paths(source_path, 'Binding.cpp'),
  join_paths(source_path, 'Binding_pch.h'),
  join_paths(source_path, 'Binding_list.cpp'),

  join_paths(source_path, 'gl', 'functions-patches.cpp'),

  # KHR binding
  join_paths(source_path, 'AbstractFunction.cpp'),
  join_paths(source_path, 'AbstractState.cpp'),
  join_paths(source_path, 'AbstractValue.cpp'),
  join_paths(source_path, 'FunctionCall.cpp'),
  join_paths(source_path, 'State.cpp')
)

letters = ['0', 'a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z']
foreach letter : letters
  libglbinding_src += join_paths(source_path, 'Binding_objects_@0@.cpp'.format(letter))
  libglbinding_src += join_paths(source_path, 'gl', 'functions_@0@.cpp'.format(letter))
endforeach

libglbinding_inc = include_directories('include')

libglbinding_lib = library('glbinding', libglbinding_src, install : true, include_directories : libglbinding_inc)

glbinding_dep = declare_dependency(
  link_with : libglbinding_lib,
  include_directories : libglbinding_inc,
  version : '3.0.2'
)
