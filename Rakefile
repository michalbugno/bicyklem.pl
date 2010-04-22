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

desc "Clear generated HTML"
task :clear do
  FileUtils.rm_rf("_site")
end

desc "Clear generated HTML and regenerate"
task :regenerate_full => [:clear, :regenerate]

desc "Deploy latest version to sezam server"
task :deploy => [:regenerate_full] do
  puts `rsync -avr _site/* sezam:public_html/bicyklem.pl`
end
