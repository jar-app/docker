task default: %w[setup]

UserService = 'user_service'
Services = [] << UserService
task :build do
  sh 'docker-compose build'
end

task :setup => [:build] do
  # Database set-up
  sh "docker-compose run #{UserService} bundle exec rake db:create"
  sh "docker-compose run #{UserService} bundle exec rake db:migrate"
end
