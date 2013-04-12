require 'rake'
require 'nanoc3/tasks'

task :gen do
  system "nanoc"
end

desc "Compile the site"
task :compile do
  `nanoc compile`
end

# prompt user for a commit message; default: HEAD commit 1-liner

def commit_message
  last_commit = `git log -1 --pretty=format:"%s"`.chomp.strip
  last_commit = 'Publishing content to GitHub pages.' if last_commit == ''

  print "Enter a commit message (default: '#{last_commit}'): "
  STDOUT.flush
  mesg = STDIN.gets.chomp.strip

  mesg = last_commit if mesg == ''
  mesg.gsub(/'/, '') # to allow this to be handed off via -m '#{message}'
end

desc "Publish to http://docs.freistilbox.com.com"
task :publish => [:clean] do
  mesg = commit_message

  FileUtils.rm_r('output') if File.exist?('output')

  sh "nanoc compile"

  ENV['GIT_DIR'] = File.expand_path(`git rev-parse --git-dir`.chomp)
  old_sha = `git rev-parse refs/remotes/origin/gh-pages`.chomp
  Dir.chdir('output') do
    ENV['GIT_INDEX_FILE'] = gif = '/tmp/docs.fb.i'
    ENV['GIT_WORK_TREE'] = Dir.pwd
    File.unlink(gif) if File.file?(gif)
    `git add -A`
    tsha = `git write-tree`.strip
    puts "Created tree #{tsha}"
    if old_sha.size == 40
      csha = `echo '#{mesg}' | git commit-tree #{tsha} -p #{old_sha}`.strip
    else
      csha = `echo '#{mesg}' | git commit-tree #{tsha}`.strip
    end
    puts "Created commit #{csha}"
    puts `git show #{csha} --stat`
    puts "Updating gh-pages from #{old_sha}"
    `git update-ref refs/heads/gh-pages #{csha}`
    `git push origin gh-pages`
  end
end
