require "bundler/gem_tasks"
require 'rubygems'
require 'rake'
require 'rake/testtask'
require 'rake/packagetask'
require 'rubygems/package_task'
require 'rspec/core/rake_task'
require 'spree/testing_support/common_rake'
require 'solidus_user_prices'

Bundler::GemHelper.install_tasks
RSpec::Core::RakeTask.new

task default: :spec

spec = eval(File.read('solidus_user_prices.gemspec'))

Gem::PackageTask.new(spec) do |p|
  p.gem_spec = spec
end

desc 'Generates a dummy app for testing'
task :test_app do
  ENV['LIB_NAME'] = 'solidus_user_prices'
  Rake::Task['common:test_app'].invoke
end