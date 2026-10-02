# Possible research projects and mini-projects

An initial set of possible research projects is provided at the end of the README in the [phonebook experiment materials](https://github.com/dnulab/onboarding/tree/main/phonebook)

Additional suggestions:

* Use "dreaming" to prevent catastrophic forgetting. Before learning new information the model should be allowed to "dream" or generate synthetic data based on its existing knowledge. When learning the new knowledge it alternates between learning on the dreamed data and learning on the new data. We might need to craft the dreams more carefully for example by ensuring they include all words in the vocab or something like that.
* Use _distillation_ to recover forgotten information. For example, learn phone book A and save this model as model A. Learn phone book B, initialized from model A, and save the result as model B. Now learn model C by _distilling_ the knowledge from models A and B. Many variants are possible:
  * Standard distillation might appear silly in this situation, because it amounts to training a model based on both sets of data i.e., both phone books. However, it is still interesting to investigate how quickly the training converges under a variety of approaches. For example, what if we initialize the distillation from model A compared to initializing from model B, and perhaps from some hybrid like A model constructed by alternately taking layers from A and B.
  * Suppose we deliberately make the problem harder by retaining the list of names in phonebooks A and B but we do not know which book they were in. So now we need to distill from both models simultaneously for any given input. Are we still able to get perfect accuracy and if so what is the extra expense of training? It could be as simple as picking the highest logit from either model and targeting that.
* Create new phone books A and B that have some kind of interdependency so that there is overlap between the information learned in model A and model B. As one possible example, imagine that the second name of a person determines the first six digits of their phone number:

    ```text
    Anra Blackmore=970-720-1840
    Camra Blackmore=970-720-8311
    Camra Blackley=686-488-8613
    Gilan Brandford=945-628-0750
    Anra Brandford=945-628-8381
    Aret Brandford=945-628-1132
    Aret Deanner=830-425-7283
    Gilan Deanner=830-425-8891
    ```

    Now we can rerun all the phone book experiments with this more complex data set in which phone book A and phone book B will share some knowledge even if their names (consider as 2-tuples) are completely disjoint. Distillation experiments will be much more interesting in this context.
