# encoding: utf-8

desc "build and run Docker container"
task :default => [:build_docker, :run_docker]

desc "build and run Debug Docker container"
task :debug => [:build_docker, :debug_docker]

desc "Remove and kill docker container"
task :rm => [:kill, :rm_docker]

desc "Run Docker image"
task :run_docker do
  sh 'docker run --name huboard2 -P --cidfile="cid" -t joshuacox/huboard2'
end

desc "Debug Run Docker image"
task :debug_docker do
  sh 'docker run --name huboard2 -P --cidfile="cid" -t joshuacox/huboard2 /bin/bash'
end

desc "Exec bash in Docker image"
task :enter do
  sh 'docker exec -i -t `cat cid` /bin/bash'
end

desc "RM Docker image"
task :rm_docker do
  sh 'docker rm `cat cid`'
  sh 'rm cid'
end

desc "Kill Docker image"
task :kill do
  sh 'docker kill `cat cid`'
end

desc "Build Docker image"
task :build_docker do
  sh 'docker build -t joshuacox/huboard2 .'
end
