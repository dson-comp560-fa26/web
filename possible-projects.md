# Possible research projects and mini-projects

An initial set of possible research projects is provided at the end of the README in the [phonebook experiment materials](https://github.com/dnulab/onboarding/tree/main/phonebook)

Additional suggestions:

* Use "dreaming" To prevent catastrophic forgetting. Before learning new information the model should be allowed to "dream" or generate synthetic data based on its existing knowledge. When learning the new knowledge it alternates between learning on the dreamed data and learning on the new data. We might need to craft the dreams more carefully for example by ensuring they include all words in the vocab or something like that.