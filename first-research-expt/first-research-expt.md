# Do your first research experiment

Create your own git repo wherever you want. Most people will choose to do it within their own GitHub account, but GitLab is another good option and there are plenty of other possible choices. Give your repo a name that includes `comp560` and your login/username e.g., `comp560-jmac`.

Create a `README.md`, a `.gitignore` suitable for Python projects, a Python virtual environment, and a `LICENSE` file. Update these whenever needed as your experiment progresses. Activate your virtual environment.

You probably have already cloned our fork of nanoGPT, [comp560-nanoGPT](https://github.com/dson-comp560-sp26/comp560-nanoGPT). If not clone it. Either way it should be installed at the same directory level as your new repo (e.g., if new repo is at `~/git/comp560-jmac` then nanoGPT should be at `~/git/comp560-nanoGPT`).

Decide on the stream of data you would like your LLM to learn. Think of something that is easy to learn based only on character-by-character information. Three examples are provided here, but you should think of your own example. Seek help if necessary.
* Example 1: Count by twos starting from a number under 100. A random stream might look like:
```
        43 45 47 49
        12 14 16 18
        96 98 100 102
        8 10 12 14
        37 39 41 43
        12 14 16 18
        ...
```
* Example 2: Translate a few words between languages. A random stream might look like:
```
        siete seven
        once eleven
        nueve nine
        uno one
        doce twelve
        nueve nine
        seis six
        diez ten
        cinco five
        diez ten
        ...
```
* Example 3: Insert spaces between characters. A random stream might look like:
```        
        cebe: c e b e
        abbacde: a b b a c d e
        dbca: d b c a
        ...
```

Create a subdirectory with the name of the experiment you would like to conduct, say `insert-spaces` for example 3 above. These instructions will continue to use example 3. Populate the new subdirectory with files and folders as in the following tree:
```
        insert-spaces
        ├── README.md
        ├── config
        ├── data
        └── out
```
Continue to update the README file in this directory with descriptions of your experiment as it evolves.

Copy the provided [`prepare.py`](prepare.py) and alter it so that it produces a sample from your chosen data stream. The version provided here produces data for the `insert-spaces` experiment in example 3 above. Run your program and make a reasonable attempt to verify that it is working correctly. Note that it produces some output files:  `meta.pkl`, `train.bin`, and `val.bin`. Move these and your Python script into a new subdirectory called `basic`, under `data`:
```
data
└── basic
    ├── meta.pkl
    ├── prepare.py
    ├── train.bin
    └── val.bin
```
Why do we put these in a new subdirectory called "basic"? Because this is our "basic" version the experiment. We may have more fancy ones later with different names and they will have their own subdirectories under `data`.

Save the provided [`basic.py`](basic.py) file into your `config` directory. 

When running a new experiment for the first time, it can be a good idea to do a complete run with a very small number of training iterations. This will identify any problems or bugs before we do longer runs. So, in the `basic.py` config file, change the value of `max_iters` to (say) 200. Now let's train our model. The working directory should be your experiment directory (`insert-spaces`) in our running example. In a bash shell or similar, the command is
```bash
NANOGPT_CONFIG=../../comp560-nanoGPT/configurator.py  python -u ../../comp560-nanoGPT/train.py config/basic.py
```
Explanation:
* `NANOGPT_CONFIG` is an environment variable that tells nanoGPT where to find its default configuration. You can set this permanently in your environment or, if running from VScode, use a `.env` file, but the above syntax is a convenient instant solution in bash.
* `python -u` runs Python with _unbuffered output_, meaning you will see any output right away.
* `../../comp560-nanoGPT/train.py` is the training script shipped with an nanoGPT.
* `config/basic.py` is your individualized configuration file which will override default configuration values.

If training completed successfully, try sampling from the trained model. We expect very bad results because of the small number of training iterations, but we are still trying to debug our workflow at this stage. The sampling command, from the same working directory, could be:
```bash
NANOGPT_CONFIG=../../comp560-nanoGPT/configurator.py  python -u ../../comp560-nanoGPT/sample.py config/basic.py --num_samples=1 --max_new_tokens=100 --seed=2345
```

Change the value of `max_iters` back to (say) 2000. Retrain the model (should be only about 3 minutes) and sample from it again.

The next step depends on your results:
* If the results look good, think of a small change you can make to your model, configuration, or data. Rerun the experiment and compare results. 
* If the results are disappointing, create a simpler data set to work on and try again. Continue to create simpler data sets until get results that look good. 

Write a very short report describing all experiments, and you are done. 



