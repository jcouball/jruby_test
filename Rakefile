require 'bundler/gem_tasks'
require 'English'
require_relative 'lib/jruby_test/version.rb'

task default: :spec

task :popen_test_jruby_windows do
  output = IO.popen(["gem.bat", "build", "-V", "jruby_test.gemspec"], &:read)
  puts output.to_s
end

task :popen_test_mri_windows do
  output = IO.popen(["gem.cmd", "build", "-V", "jruby_test.gemspec"], &:read)
  puts output.to_s
end

task :popen_test_no_extension do
  puts "ENV['PATHEXT'] = '#{ENV['PATHEXT']}'"
  output = IO.popen(["gem", "build", "-V", "jruby_test.gemspec"], &:read)
  puts output.to_s
end

# if RUBY_PLATFORM == 'java'
#   Rake::Task[:build].clear
#   version = JrubyTest::VERSION
#   pkg_name = 'jruby_test'
#   gem_file = "pkg/#{pkg_name}-#{version}.gem"
#   task :build do
#     FileUtils.mkdir 'pkg' unless File.exist? 'pkg'
#     puts `gem build #{pkg_name}.gemspec --output "#{gem_file}" --quiet`
#     puts "#{pkg_name} #{version} built to #{gem_file}." if $CHILD_STATUS.success?
#   end
#   CLOBBER << gem_file
# end
