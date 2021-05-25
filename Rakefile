# frozen_string_literal: true

require 'bundler/gem_tasks'

task default: :test

desc 'Download dart-sass-embedded'
task :extconf do
  system('make', '-C', 'ext/sass_embedded', 'distclean')
  require_relative 'ext/sass_embedded/extconf'
  system('make', '-C', 'ext/sass_embedded', 'install')
end

desc 'Run all tests'
task :test do
  $LOAD_PATH.unshift('lib', 'test')
  Dir.glob('./test/**/*_test.rb').sort.each { |f| require f }
end
