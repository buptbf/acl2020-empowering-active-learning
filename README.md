# Empowering Active Learning toJointly Optimize System and User Demands
### Ji-Ung Lee, Christian M. Meyer, and Iryna Gurevych
#### [UKP Lab, TU Darmstadt](https://www.informatik.tu-darmstadt.de/ukp/ukp_home/index.en.jsp)

Source code and user models from our experiments of our [ACL 2020 article](to appear). 

<!--
```
@inproceedings{lee-etal-2019-manipulating,
    title = "Manipulating the Difficulty of C-Tests",
    author = "Lee, Ji-Ung and Schwan, Erik and Meyer, Christian M.",
    booktitle = "Proceedings of the 57th Annual Meeting of the Association for Computational Linguistics",
    month = jul,
    year = "2019",
    address = "Florence, Italy",
    publisher = "Association for Computational Linguistics",
    url = "https://www.aclweb.org/anthology/P19-1035",
    pages = "360--370",
}
```
-->

> **Abstract:** Existing approaches to active learning maximize the system performance by sampling unlabeled instances for annotation that yield the most efficient training. However, when active learning is integrated with an end-user application, this can lead to frustration for participating users, as they spend time labeling instances that they would not otherwise be interested in reading. In this paper, we propose a new active learning approach that jointly optimizes the seemingly counteracting objectives of the active learning system (training efficiently) and the user (receiving useful instances). We study our approach in an educational application, which particularly benefits from this technique as the system needs to rapidly learn to predict the appropriateness of an exercise to a particular user, while the users should receive only exercises that match their skills. We evaluate multiple learning strategies and user types with data from real users and find that our joint approach better satisfies both objectives when alternative methods lead to many unsuitable exercises for end users.

* **Contact person:** Ji-Ung Lee, lee@ukp.informatik.tu-darmstadt.de
    * UKP Lab: http://www.ukp.tu-darmstadt.de/
    * TU Darmstadt: http://www.tu-darmstadt.de/

Drop me a line or report an issue if something is broken (and shouldn't be) or if you have any questions.

For license information, please see the LICENSE and README files.

> This repository contains experimental software and is published for the sole purpose of giving additional background details on the respective publication. 

## Project structure

* `active_learning` &mdash; Our active learning strategies
* `data` &mdash; Folder to put the data
* `learner_models` &mdash; Our simulated learner models
* `models` &mdash; Folder for storing our trained deep learning models
* `readers` &mdash; Datareader
* `results` &mdash; Result folder
* `user_simulation` &mdash; Code the handing simulated learner models 

## Setting up the experiments

```python
pip install -r requirements.txt
```
## Running the experiments

```python
python train_model.py
```
### Parameters
The code offers a range of parameters which can be set:
`--train` &mdash; Path to the (initially unlabeled) training data.
`--test` &mdash; Path to the test data.
`--seed` &mdash; Random seed to use.
`--epochs` &mdash; Number of epochs.
`--init-weights` &mdash; Path to the initial model weights.
`--best-model`  &mdash; Path to store best model on the validation set.
`--sampling-strategy` &mdash; Sampling strategy: `random`, `uncertainty`, `user`, `combined`, or `tradeoff`
`--user-static-class` &mdash; Learner proficiency for the static.
`--user-step-size` &mdash; Step size t for the increasing or decreasing learner behavior. 
`--user-strategy` &mdash; Learner behavior: `increasing` (motivated), `decreasing`, `interruped`, or `static`
`--al-iterations` &mdash; Number of active learning iterations.
`--history`  &mdash; Path to the active learning history; stores the user proficiency at each iteration and the individual gap predictions
`--results`  &mdash; Path to the result file.
`--uncertainty` &mdash; Parameter for selecting the uncertainty computation. Set to `softmax` for U_soft.
`--lambda-schedule` &mdash; Schedule for an adaptive lambda. `None` (static lambda) or `root` for a decreasing lambda.



<!--
## Experiments

### Requirements

* Java 1.7 and higher, Maven (for Java-based experiments)
* Python 2.7 and `virtualenv` (for Python-based experiments)
    * GPU is recommended but not required
* Tested on 64-bit Linux versions
-->


