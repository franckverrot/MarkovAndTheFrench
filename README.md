# Markov Chain and French politics

This repository is a proof-of-concept of building a Markov chain of some of
the French politics, and exploiting it for fun and profit.

The first chain I built is the one of our former Président, but as soon as
I can compile more quotes from the newest Président or from other politics,
I will update this repository.

## Usage

    λ rake -T
    rake generate_chain  # Generate the chain file from the quotes
    rake get\_quote       # Load the chain file and get a quote

    λ rake generate_chain

    λ rake get_quote
    ... some quote ...

### Examples :-)

    La formation professionnelle ne va pas dans la société calédonienne, la France redevient une terre de recherche.

    Les socialistes veulent la justice.

    La France n’est pas la croissance.

    La France est intervenue pour protéger et le peuple de France dit « ça suffit »

    Ce grand emprunt pour financer les micros projets.


## License

Franck Verrot, Copyright 2014. MIT License.
The quotes are not part of this licensing as they belong to their author, who
ever they are.

## Contribute

Please help and:

1. Contribute new quotes;
2. Find a way for discarding quotes that make no sense at all.
3. ???
4. PROFIT!!!1!
