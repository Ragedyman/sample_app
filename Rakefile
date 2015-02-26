#!/usr/bin/env rake
# Add your own tasks in files placed in lib/tasks ending in .rake,
# for example lib/tasks/capistrano.rake, and they will automatically be available to Rake.

require 'active_support/core_ext'

guard 'rspec', :version => 2, :all_after_pass => false do
  .
  .
  .
  watch(%r{^app/controllers/(.+)_(controller)\.rb$})  do  |m|
    ["spec/routing/#{m[1]}_routing_spec.rb"
     "spec/#{m[2]}s/#{m[1]}_#{m[2]}_spec.rb",
     "spec/acceptance/#{m[1]}_spec.rb",
     (m[1][/_pages/] ? "spec/requests/#{m[1]}_spec.rb" :
                       "spec/requests/#{m[1].singluarize}_pages_spec.rb")]
  end
  watch(%r{^app/views/(.+)/}) do |m|
    "spec/requests/#{m[1].singularize}_pages_spec.rb"
  end
  .
  .
  .
end
