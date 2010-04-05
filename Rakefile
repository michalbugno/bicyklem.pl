require 'rubygems'
require 'rake'

desc "Start server"
task :server do
  puts `jekyll --auto --server`
end

desc "Regenerate site"
task :regenerate do
  puts `jekyll`
end

desc "Deploy latest version to sezam server"
task :deploy => [:regenerate] do
  puts `rsync -avr _site/* sezam:public_html/bicyklem.pl`
end
