require 'rake'

task :default => :build

desc "Build a compacted crypto.js file"
task :build do
  require 'lib/jsmin'

  # compact all js files into a single compacted file
  crypto_files = 
  ['base.js', 'reduction/classic.js', 'reduction/montgomery.js', 
   'bigint.js', 'secure_states.js', 'secure_random.js', 'rsa.js']

  File.open("crypto.js", "w") do|f|
    crypto_files.each do|file|
      puts "add #{file}"
      f << JSMin.minify(File.read("src/#{file}"))
    end
  end

end
