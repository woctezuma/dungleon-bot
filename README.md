# Dungleon Bot

This repository contains Python code to find the best starter guesses for Dungleon.

[![Dungleon][img-cover]][game]

## Characters

[![Sprites][img-sprites]][img-sprites-original]

As official emojis:
:bow_and_arrow: :bat: :moneybag: :yellow_circle: :dragon_face: :frog: :japanese_goblin: :crown: 🧙‍♀️ :imp: :japanese_ogre: :skull: :spider: :bust_in_silhouette: 🤡 :trophy: :man_farmer: :person_fencing: 🧙‍♂️ :zombie:

## Algorithms

I have collected a few open-source algorithms:
- `Simple` maximizes the number of points attributed to guess feedbacks: 🟧 (2 points), 🟦 (1 point), ⬛ (0 point).
- `Complex` minimizes the cardinality of the set of remaining solutions after each guess.
- `MinMax` optimizes for the "worst case" scenario.
- `MaxEntropy` maximizes the entropy of the set of patterns.

For each algorithm, there are two versions:
- constrained: guesses are constrained to the set of **valid** solutions.
- unconstrained: the set of guesses is 5-6 times larger, as **invalid** solutions are allowed.

**Caveat**: the `Complex` algorithm is very slow!
Avoid using it if possible, because the results are not much different to other algorithms anyway.

## Usage

-   Run [`dungleon-bot.ipynb`][colab-notebook]
[![Open In Colab][colab-badge]][colab-notebook]

## Results

### Constrained

- `Simple`
![Simple][results-constrained-simple]
- `Complex`
![Complex][results-constrained-complex]
- `MinMax`
![MinMax][results-constrained-minmax]
- `MaxEntropy`
![MaxEnt][results-constrained-maxent]

### Unconstrained

- `Simple`
![Simple][results-unconstrained-simple]
- `Complex`
![Complex][results-unconstrained-complex]
- `MinMax`
![MinMax][results-unconstrained-minmax]
- `MaxEntropy`
![MaxEnt][results-unconstrained-maxent]

## Perspectives

As in Wordle, Dungleon features a hard mode ![Crystal][img-crystal], where "any revealed hints must be used in subsequent guesses".
Future development of the Dungleon Bot could take into account this additional difficulty.

In Dungleon, guess feedbacks mention if a character appears several times with a `+` in the top right corner of the character tile.
This additional piece of information could be taken into account by the Dungleon Bot.

## References

- The [official website][game]
- A study of [the hidden rules][dungleon-rules] of Dungleon
- Solvers for [Wordle][wordle-game]:
  - Tyler Glaiel, [The mathematically optimal first guess in Wordle][wordle-bot-cpp-blog-post], December 2021
  - [`TylerGlaiel/wordlebot`][wordle-bot-cpp] (`Simple`, `Complex`, `MinMax` in C++)
  - [`GillesVandewiele/Wordle-Bot`][wordle-bot-python] (`MaxEntropy` in Python)

[game]: <https://www.dungleon.com/>
[img-cover]: <https://github.com/woctezuma/dungleon-bot/wiki/img/cover.png>
[img-sprites]: <https://github.com/woctezuma/dungleon-bot/wiki/img/sprites/big.png>
[img-crystal]: <https://github.com/woctezuma/dungleon-bot/wiki/img/sprites/crystal.png>
[img-sprites-original]: <https://www.dungleon.com/images/elements/big/sprites.png>
[dungleon-rules]: <https://github.com/woctezuma/dungleon>
[wordle-game]: <https://www.nytimes.com/games/wordle>
[wordle-bot-cpp-blog-post]: <https://medium.com/@tglaiel/the-mathematically-optimal-first-guess-in-wordle-cbcb03c19b0a>
[wordle-bot-cpp]: <https://github.com/TylerGlaiel/wordlebot>
[wordle-bot-python]: <https://github.com/GillesVandewiele/Wordle-Bot>
[results-constrained-simple]: <https://github.com/woctezuma/dungleon-bot/wiki/img/results/constrained/cpp_simple.png>
[results-constrained-complex]: <https://github.com/woctezuma/dungleon-bot/wiki/img/results/constrained/cpp_complex.png>
[results-constrained-minmax]: <https://github.com/woctezuma/dungleon-bot/wiki/img/results/constrained/cpp_minmax.png>
[results-constrained-maxent]: <https://github.com/woctezuma/dungleon-bot/wiki/img/results/constrained/python_maxent.png>
[results-unconstrained-simple]: <https://github.com/woctezuma/dungleon-bot/wiki/img/results/unconstrained/cpp_simple.png>
[results-unconstrained-complex]: <https://github.com/woctezuma/dungleon-bot/wiki/img/results/unconstrained/cpp_complex.png>
[results-unconstrained-minmax]: <https://github.com/woctezuma/dungleon-bot/wiki/img/results/unconstrained/cpp_minmax.png>
[results-unconstrained-maxent]: <https://github.com/woctezuma/dungleon-bot/wiki/img/results/unconstrained/python_maxent.png>
[colab-notebook]: <https://colab.research.google.com/github/woctezuma/dungleon-bot/blob/colab/dungleon-bot.ipynb>
[colab-badge]: <https://colab.research.google.com/assets/colab-badge.svg>
