# PCFG Conditional Entropy Calculator

A fast, easy-to-install and scalable PCFG conditional probability and conditional entropy calculator. 



Beta version. If something went wrong, please first check the [FAQs](#FAQs) and feel free to [contact the author](mailto:freda@ttic.edu) or directly raise an issue in this repo if you had questions or comments. 

## Dependencies
Python >= 3.7 <br>
scipy >= 1.2.1 <br>

## Demo
```
python compute.py -s "Jon hit the dog with the stick" -g ./data/strauss.pcfg
```

## FAQs
- Why the entropy/probability is NaN? <br>
    - Check if all words in your sentences appear in your given grammar. 

- Why RuntimeError? <br>
    - Check if the given grammar is *consistent* (i.e., the probability of all generated sentences from the root node (`S` by default) sums up to 1). The current system does not support inconsistent grammars. 
    
- Does the current calculator support grammars with left recursions?
    - Yes! 
    - Check if there is left recursion in your grammar using ``check_left_recursion.py``. 
    For more details about what left recursion is and why it matters, see [Hale (2003)](http://www.umiacs.umd.edu/~ymarton/ling849b/hale2003.pdf) and the [Wikipedia page](https://en.wikipedia.org/wiki/Left_recursion). 

- Does the current calculator support empty terminal?
    - No, but it is possible to extend it by simply modifying some code of the functions `calc_inside` and `conditional_entropy`.

## Citation
if you found the tool useful, please consider citing it as follows before an accompanying paper is ready:
```
@software{shi2019pcfg,
  author = {Freda Shi},
  title = {PCFG Conditional Entropy Calculator},
  url = {https://github.com/explorerfreda/conditional-entropy}
}
```

## Acknowledgement
This tool calculates PCFG conditional entropy defined by [Hale(2003)](http://www.umiacs.umd.edu/~ymarton/ling849b/hale2003.pdf), as [CCPC](https://github.com/timhunter/ccpc) does. 
The example data are from [CCPC](https://github.com/timhunter/ccpc).
