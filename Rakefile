require 'rake'
require 'nanoc3/tasks'

task :publish do
  system "cd output"
  system "git add ."
  system "git commit"
  system "git push"
end
