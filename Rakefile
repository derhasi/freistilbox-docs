require 'rake'
require 'nanoc3/tasks'

task :gen do
  system "nanoc"
end

task :publish => :gen do
  chdir "output"
  system "git add ."
  system "git commit"
  system "git push"
end
