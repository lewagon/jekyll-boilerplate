require "date"

task :post do
  puts "Quel est le titre de votre nouvel article de blog ?"
  print "> "
  title = STDIN.gets.chomp
  slug = "#{Date.today}-#{title.downcase.gsub(/[^\w]+/, '-')}"

  file = File.join(
    File.dirname(__FILE__),
    '_posts',
    slug + '.markdown'
  )

  File.open(file, "w") do |f|
    f << <<-EOS.gsub(/^    /, '')
    ---
    layout: post
    category: blog
    title: #{title}
    ---

    EOS
  end
end