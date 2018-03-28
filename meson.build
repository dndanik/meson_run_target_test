project('run_target_test', 'cpp')

python = find_program('python', required : true)

test_exe = executable('test_exe',
  sources: 'main.cpp',
)

cfg = configuration_data()
cfg.set_quoted('PATH', test_exe.full_path())

run_script = configure_file(
  configuration : cfg,
  input : 'launcher.py.in',
  output : 'launcher.py'
)

run_target('launch',
  command : [python, run_script],
  depends : test_exe,
)
