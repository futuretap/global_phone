require 'rake/testtask'
require 'bundler'

Bundler.setup
Bundler::GemHelper.install_tasks

task :default => :test

Rake::TestTask.new do |t|
  t.libs << "test"
  t.test_files = FileList["test/*_test.rb"]
  t.warning = true
end

task :gems do
  Dir["*.gemspec"].each do |gemspec|
    system "gem build #{gemspec}"
  end
end
