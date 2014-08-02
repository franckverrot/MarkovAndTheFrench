require 'pp'

desc "Generate the chain file from the quotes"
task :generate_chain do
  def generate_trigram(words)
    return if words.size < 3
    (words.size - 2).times do |i|
      yield words[i..i+2]
    end
  end

  chain = {}
  File.open("quotes.txt", "r") do |f|
    f.readlines.each do |line|
      words = line.split()
      generate_trigram(words) do |word1, word2, word3|
        key = [word1, word2]
        if chain.key?(key)
          chain[key] << word3
        else
          chain[key] = [word3]
        end
      end
    end
  end

  File.open("sarko.chain", "wb") do |f|
    Marshal.dump(chain, f)
  end
end

desc "Load the chain file and get a quote"
task :get_quote do
  chain = File.open("sarko.chain", "rb") { |f| Marshal.load(f) }

  while true
    new_review = []
    sword1 = "BEG"
    sword2 = "CHAIN"

    while true
      c = chain[[sword1, sword2]]
      sword1, sword2 = sword2, c.sample
      break if sword2 == "ENDCHAIN"
      new_review << sword2
    end
    if new_review.size > 40
      next
    end

    puts new_review.join(' ')
    puts "\nAppuyez sur entrée pour une nouvelle citation!\n"
    $stdin.getc
  end
end
