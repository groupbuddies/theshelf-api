# Add your own tasks in files placed in lib/tasks ending in .rake,
# for example lib/tasks/capistrano.rake, and they will automatically be available to Rake.

require File.expand_path('../config/application', __FILE__)
TheShelf::Application.load_tasks

if %w(development test).include? Rails.env
  require 'rubocop/rake_task'

  RuboCop::RakeTask.new
  Rake::Task[:default].prerequisites.clear

  task default: [:rubocop, :spec]
end
