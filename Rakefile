require 'rubygems'
require 'bundler'
require 'rake/tasklib'
require 'rake/rdoctask'

begin
  Bundler.setup(:default, :development)
rescue Bundler::BundlerError => e
  $stderr.puts e.message
  $stderr.puts "Run `bundle install` to install missing gems"
  exit e.status_code
end
require 'rake'

require 'rspec/core/rake_task'
RSpec::Core::RakeTask.new do |t|
  t.pattern = FileList['./spec/**/*_spec.rb']
end
  
task :default => :spec

Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "equivalent-xml #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
