examples = [
  'actor-model',
  'basic-actor',
  'box-layout',
  'canvas',
  'constraints',
  'drag-action',
  'drop-action',
  'easing-modes',
  'flow-layout',
  'grid-layout',
  'layout-manager',
  'pan-action',
  'rounded-rectangle',
  'scroll-actor',
  'threads',
]

examples_deps = [
  libclutter_dep,
]

enable_pixbuf_tests = get_option('pixbuf_tests')
if enable_pixbuf_tests
  examples += [
    'bin-layout',
    'image-content',
  ]

  examples_deps += [
    dependency('gdk-pixbuf-2.0'),
  ]
endif

examples_cargs = []

if cc.get_argument_syntax() == 'msvc'
  examples_cargs += '-D_USE_MATH_DEFINES'
endif

foreach e: examples
  executable(
    e,
    e + '.c',
    dependencies: examples_deps,
    c_args: examples_cargs,
  )
endforeach
