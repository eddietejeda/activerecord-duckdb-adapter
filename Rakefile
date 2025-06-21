# frozen_string_literal: true

require "bundler/gem_tasks"
require "rake/testtask"

Rake::TestTask.new(:test) do |t|
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList["test/**/*_test.rb"]
  t.warning = true
  t.verbose = true
end

begin
  require "rubocop/rake_task"
  RuboCop::RakeTask.new
  task default: %i[test rubocop]
rescue LoadError
  # RuboCop not available, skip it
  task default: %i[test]
end

