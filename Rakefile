task default: %w[setup]

UserService = 'user_service'

# List of all services
Services = [] << UserService

task :setup => [:build] do
  # Database set-up
  while true
    begin
      sh "docker-compose run #{UserService} bundle exec rake db:create db:migrate"
    rescue
      sleep 1
    else
      break
    end
  end
end

task :clean_start => [:clean, :setup] do
  Rake::Task["start"].invoke
end

task :start do
  sh 'docker-compose up --abort-on-container-exit'
end

task :build => [:clean] do
  sh 'docker-compose build'
end

task :clean do
  sh 'docker-compose down; true'
  sh 'rm -rv user_service/tmp/*; true'
end
