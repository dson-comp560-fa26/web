# Onboarding activities

This is a list of activities that are recommended to be completed as part of joining the research project. You can begin working on these at the start of the Spring 2026 semester. Optionally, you can complete some or all of these activities during the winter break. The activities are listed in one possible ordering but they can be done in a different order. Tackle them according to your own interests and preference.

## Introduction and activity log
* Introduce yourself on the [Introductions channel](https://teams.microsoft.com/l/channel/19%3A04cf6900377e482a8e6d7efb5d0ee439%40thread.tacv2/Introductions?groupId=327c5cf0-93db-45ce-be36-d648004b666f&tenantId=6232b055-76b9-4c13-9b88-b562ae7db6fb).
* Create a new private channel in our Team to act as your _activity log_. See the separate [Activity Logs page](activity-logs.md) for details.

## Preparatory reading

* Easy intro to LLMs: Read the chapter on Generative AI from jmac's forthcoming book: [maccormick-thinkingAI-ch10.pdf](https://dickinson0.sharepoint.com/:b:/r/sites/COMP560spring2026/Shared%20Documents/General/literature/maccormick-thinkingAI-ch10.pdf?csf=1&web=1&e=fuMXU7) -- this link is restricted to members the COMP560 MS Team -- more details on the book at [Princeton University Press](https://press.princeton.edu/books/hardcover/9780691191737/thinking-ai) or [Amazon](https://www.amazon.com/Thinking-AI-Artificial-Intelligence-Understanding-ebook/dp/B0FTKHZ676/).
* Read Feng, G., Zhang, B., Gu, Y., Ye, H., He, D., &amp; Wang, L. (2023). [Towards revealing the mystery behind chain of thought: a theoretical perspective.](https://proceedings.neurips.cc/paper_files/paper/2023/file/dfc310e81992d2e4cedc09ac47eff13e-Paper-Conference.pdf) _Advances in Neural Information Processing Systems_, 36, 70757-70798.
  - **Don't worry about the math.**
  - Just try to understand some of their practical experiments.
  - If you have questions, please post discussion on the [Feng2023 Teams channel](https://teams.microsoft.com/l/channel/19%3A6df87f59d4de410b8a2a75e94f6b0c7c%40thread.tacv2/Feng2023?groupId=327c5cf0-93db-45ce-be36-d648004b666f&tenantId=6232b055-76b9-4c13-9b88-b562ae7db6fb).
* Read Baeumel, Tanja, Josef van Genabith, and Simon Ostermann. ["The lookahead limitation: Why multi-operand addition is hard for LLMs."](https://arxiv.org/pdf/2502.19981)
  - Focus on the experimental results. Don't worry about theoretical ideas.

## GitHub and pull requests

* Practice submitting a pull request to our public website:
  - fork the repo at [https://github.com/dson-comp560-sp26/comp560-web](https://github.com/dson-comp560-sp26/comp560-web)
  - Add your name and any optional links to the `participants.md` file.
  - Submit a pull request (PR) for the change. Ask for help on Teams and/or from an AI assistant if you don't know how to do this.

## NanoGPT familiarization
  * Download and familiarize yourself with Andrej Karpathy's [nanoGPT](https://github.com/karpathy/nanoGPT). If you have questions or need help, post to the [nanoGPT channel](https://teams.microsoft.com/l/channel/19%3Adeeefd292f9d470d93d60bad64e6ab7e%40thread.tacv2/nanoGPT?groupId=327c5cf0-93db-45ce-be36-d648004b666f&tenantId=6232b055-76b9-4c13-9b88-b562ae7db6fb).
    1. Figure out how to train and sample from the _character-level_ Shakespeare model.
    2. Create a new character-level model that is identical to the character-level Shakespeare model but using a different corpus of text. 
  * Train and sample from the character-level Shakespeare model in _our fork of nanoGPT_: [comp560-nanoGPT](https://github.com/dson-comp560-sp26/comp560-nanoGPT)
    - This should be very similar to the previous exercise, but you have the capability of training and sampling from a different directory. See the `README-fork.md` file in that repo.
  * Train and sample from the models in [comp560-jmac](https://github.com/dson-comp560-sp26/comp560-jmac). See the README there.
    - Also, add your name to the "building_blocks" list in `alphabet/data/students/prepare.py`. Train and sample from the model again to verify it can output your name (among the other random choices) when sampling.
    - Submit a PR for your change.


## Do your first research experiment

  * Instructions for this are on the separate [First Research Experiment](first-research-expt/first-research-expt.md) page

## Wandb familiarization

* Sign up at [wandb.ai/](https://wandb.ai/). Make sure you are a member of our team `dickinson-comp560-sp26`. (You should have received an invitation for this. If not, you can request one from the instructors.)
* Do a tutorial available from Wandb. Make sure you view can results from a run of their tutorial code.
* Re-run your [First Research Experiment](first-research-expt/first-research-expt.md), this time using Wandb for logging. 
  - In the config file, set `wandb_log = True` and provide meaningful values for `wandb_project` and `wandb_run_name`.
* View the results at [wandb.ai/](https://wandb.ai/). Ensure you can see a graph of the training loss decreasing as the number of iterations increases. Add this graph to the report you made on your first research experiment.
