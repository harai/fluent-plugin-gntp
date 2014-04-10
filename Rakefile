require 'rake'
require 'rake/testtask'
require 'rake/clean'

begin
	require 'jeweler'
	Jeweler::Tasks.new {|gemspec|
		gemspec.name = "fluent-plugin-gntp"
		gemspec.summary = "GNTP output plugin for Fluent Event Collector"
		gemspec.authors = ["Akihiro Harai", "TAKEI Yuya"]
		gemspec.email = "jharai0815@gmail.com"
		gemspec.homepage = "https://github.com/harai/fluent-plugin-gntp"
		gemspec.has_rdoc = false
		gemspec.require_paths = ["lib"]
		gemspec.add_dependency "fluentd", "~> 0.10.0"
		gemspec.add_dependency "ruby_gntp", "~> 0.3.4"
		gemspec.test_files = Dir["test/**/*.rb"]
		gemspec.files = Dir["bin/**/*", "lib/**/*", "test/**/*.rb"] + %w[VERSION AUTHORS Rakefile LICENSE]
		gemspec.executables = []
	}
	Jeweler::GemcutterTasks.new
rescue LoadError
	puts "Jeweler not available. Install it with: gem install jeweler"
end

Rake::TestTask.new(:test) {|t|
	t.test_files = Dir['test/*_test.rb']
	t.ruby_opts = ['-rubygems'] if defined? Gem
	t.ruby_opts << '-I.'
}

task :default => [:build]
