# walkthrough make sure they go through piece by piece
# 1. add namespace greeting and hola greeting inside of it. 
# 2. namespace for migration(run rake db:migrate)
# 3.add environment task top of rakefile
# 4. add seed to end of the db namespace (run rake db:seed)
# 5. add console to bottom of rakafile 
task :environment do
  require_relative './config/environment'
end

namespace :greeting do
  desc 'outputs hello to the terminal'
  task :hello do
    puts "hello from Rake!"
  end

  desc 'outputs hola to the terminal'
  task :hola do
    puts "hola de Rake!"
  end
end

namespace :db do 
  desc 'migrate changes to your database'
  task :migrate => :environment do
    Student.create_table
  end

  desc 'seed the database with some dummy data'
  task :seed do
    require_relative './db/seeds.rb'
  end


end

desc 'drop into the Pry console'
task :console => :environment do
  Pry.start
end
