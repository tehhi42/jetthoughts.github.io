desc "compile and run the site"
task :default do
  pids = [
    spawn("compass watch"),
    spawn("jekyll serve -w")
    #spawn("coffee -b -w -o javascripts -c _assets/*.coffee")
  ]

  trap "INT" do
    Process.kill "INT", *pids
    exit 1
  end

  loop do
    sleep 1
  end
end