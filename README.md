# Debate Auto Highlighter

This notebook is a tool to help highlight the important parts of a piece of evidence in Policy Debate, hoping to make this frustrating process more efficient. It is currently a work in progress, although it can be used for very simple highlighting.

The notebook fine tunes the [Longformer](https://huggingface.co/docs/transformers/model_doc/longformer) transformer model, which has an attention mechanism that scales with the longer debate cards. To fine tune this model, it uses data from [DebateSum](https://github.com/Hellisotherpeople/DebateSum), learning what tokens to highlight based on the data from real debaters.

## Usage

Open the `main.ipynb` in the Jupyter Notebook editor of your choice, and run all the cells. The notebook was created in [Google Colab](https://colab.research.google.com/), but can be run locally if your computer is powerful enough.

Because the Longformer model and the inputs are so big, the batch_size is significantly smaller than normal to prevent memory errors. If you have access to a mighty computer, you can increase the batch_size to speed up the training process.

## Results

When trained, the model achieves a ~75% accuracy on the validation set. It highlights words and phrases relevant to the tag, but has trouble creating coherent sentences. These results can probably be improved with more training and a better way to represent the already highlighted words.
