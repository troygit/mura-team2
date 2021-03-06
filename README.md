# MURA Team 2 Repo

This repo will be mainly designated for collaboratively learning about CV and showcasing our work on the MURA competition.

### Planned folder structure:
```
├── data
│   ├── MNIST_data
│   └── MURA-v1.1
│       ├── train
│       └── valid
├── models
├── setup
└── utils
```

- data: contains the MURA dataset and MNIST dataset. Note that this folder is not uploaded to github
- models: to contain all the model scripts and stored models
- setup: contains the instructions to setup environment and datasets
- utils: stores useful scripts so that we can import to our notebooks.

Note that this structure is preliminary. If it's deemed not flexible enough as we progress we'll update it

## Notebooks:

### [0_0_keras_tutorial_with_mnist.ipynb](0_0_keras_tutorial_with_mnist.ipynb)
A tutorial for Keras on MNIST. Taken from https://elitedatascience.com/keras-tutorial-deep-learning-in-python

### [0_1_read_pickle_mura_data.ipynb](0_1_read_pickle_mura_data.ipynb)
A wrapper for importing MURA images as grayscale, padding them to be a square, reshaping and saving the resulting numpy array into a pickle file

### [0_2_keras_tutorial_with_mura.ipynb](0_2_keras_tutorial_with_mura.ipynb)
The same tutorial, just on MURA dataset now

### [0_3_notes_on_cohens_kappa.ipynb](0_3_notes_on_cohens_kappa.ipynb)
Some notes on the mathematical properties of Cohen's Kappa

### [1_1_resnet50_mura.ipynb](1_1_resnet50_mura.ipynb)
Using the resnet50 predefined in Keras to train on MURA data
- Accuracy on training set is above 99%, but on test set is 69%: possible over fit
- trying with image pertubation to reduce overfit
    - With image pertubation, kappa starts to correlate with training set accuracy - good sign

### [1_3_densenet_mura.ipynb](1_3_densenet_mura.ipynb)
- Better results in the first 50 epoches than resnet (kappa=0.44)


## Next steps:
- FN seems to be much larger than FP - maybe we should adjust prediction to a balanced sample?
- More on Cohen's kappa - Can we maximize it given accuracy?
- Streamline model evaluation
- Generate model performance by body parts - if a body part is significantly different, maybe we should train a separate model
- extract middle layer activation patterns - is our algo looking at the right place?
- More ways to prevent overfit?
- Try using WGAN to generate more sample for training?
- other forms of models, e.g. activation model?
