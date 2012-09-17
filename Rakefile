IMAGE_PATTERN = "tmp/img-%09d.jpg"

task :default => :movie

desc "build movie"
task :movie do
  if Dir.glob("tmp/*").empty?
    puts "No image sequence found. Have you run `rake sequence`?"
    return
  end

  command = ["ffmpeg", "-f", "image2", "-r", "10", "-i", IMAGE_PATTERN]

  if audio_file = Dir.glob("audio/*").first
    command += ["-i", audio_file]
    command += ["-map", "0:0", "-map", "1:0"]
    command += ["-shortest"]
  end

  command << "out.mp4"

  sh *command
end

desc "build sequence of image files"
task :sequence do
  sh "rm -rf tmp"
  sh "mkdir tmp"

  Dir["images/*.jpg"].each_with_index do |path, index|
    tmp_path = (IMAGE_PATTERN % [index+1])
    next if File.exists?(tmp_path)
    sh "ln", "-s", File.expand_path(path), tmp_path
  end
end
