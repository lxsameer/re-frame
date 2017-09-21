desc "Deploy _site/ to gh-pages branch"
task :deploy do
  system("git stash")
  system("git branch -D gh-pages")
  system("git checkout --orphan gh-pages")
  system("git rm -rf ./*")
  system("cp -r ./build/* ./ ")
  system("echo 're-frame.lxsameer.com' > CNAME")
  system("git add .")
  system("git commit -a -m \"Release at #{Time.now.utc}\"")
  system("git push mine gh-pages -f")
  system("git checkout master")
  system("git stash apply")
end

task :default => :deploy
