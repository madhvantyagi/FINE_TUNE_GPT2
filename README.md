# Fine-Tuned GPT-2 Model for Song Lyrics Generation

Welcome to the Fine-Tuned GPT-2 Model project! This repository contains a Jupyter notebook that implements a fine-tuned version of the GPT-2 model, specifically designed to generate song lyrics. By leveraging a collection of lyrics from various American singers, this model can produce creative and coherent song lyrics based on user-provided prompts.

## Overview

The GPT-2 model, developed by OpenAI, is a state-of-the-art language model that has been widely used for various natural language processing tasks. In this project, we have fine-tuned the GPT-2 model on a dataset of American singers' song lyrics. The training process involved preprocessing the lyrics, training the model, and evaluating its performance. The result is a model capable of generating unique and contextually relevant lyrics.

## Dataset

The model was trained on a comprehensive dataset comprising song lyrics from a diverse collection of American singers. This dataset was curated to expose the model to various lyrical styles, themes, and structures prevalent in American popular music. The raw lyrics were processed and tokenized into numerical representations suitable for the GPT-2 architecture. The tokenized data is stored in the `combined_artists_tokenized.csv` file.

## Training Process

The fine-tuning process involved adapting a pre-trained GPT-2 model (`gpt2`) to the specific task of lyric generation using the collected dataset. Key aspects of the training included:

*   **Data Loading and Preprocessing**: Lyrics were loaded from the CSV, converted from token strings to lists, and prepared into a custom PyTorch Dataset (`LyricsDataset`). Each lyric sequence was padded or truncated to a fixed `max_length` (1024 tokens).
*   **Model and Tokenizer**: The standard `gpt2` model and tokenizer from the `transformers` library were used.
*   **Training Configuration**: The model was trained using the AdamW optimizer with a linear learning rate scheduler. Training was performed for 3 epochs with a batch size of 4.
*   **Hardware**: Training was configured to utilize a GPU if available, falling back to CPU otherwise.
*   **Model Saving**: The model and tokenizer were saved periodically based on validation loss to the `fine_tuned_gpt2_lyrics` directory.

## How to Use the Model

To generate song lyrics using the fine-tuned model, follow these steps:

1.  **Clone the Repository**: Download or clone this repository to your local machine.
2.  **Install Required Libraries**: Ensure you have the necessary libraries installed. You can do this by running:
    ```bash
    pip install -r requirements.txt
    ```
    (Note: You may need to create a `requirements.txt` file listing the dependencies like `pandas`, `numpy`, `torch`, `transformers`, `tqdm`, `sklearn`).
3.  **Open the Jupyter Notebook**: Launch Jupyter Notebook or JupyterLab and open the [`lyrical-gpt2.ipynb`](lyrical-gpt2.ipynb) file located in the `FINE_TUNE` directory.
4.  **Run the Notebook Cells**: Execute the cells sequentially.
    *   The initial cells load libraries, set up the device, load and preprocess the dataset.
    *   The training cells (Epoch 1, 2, 3) will train the model. This step can take a significant amount of time depending on your hardware. You can skip these if you have already trained the model and have the saved `fine_tuned_gpt2_lyrics` directory.
    *   The final cells load the fine-tuned model and tokenizer and provide a function (`generate_lyrics`) to generate lyrics based on a prompt.
5.  **Generate Lyrics**: In the final cell block, you will be prompted to "Enter your song lyrics : ". Type a starting phrase or line and press Enter. The model will generate a continuation of the lyrics.

## Demonstration

To showcase the capabilities of the fine-tuned model, a demonstration video (`Sample.mp4`) is included in this repository.

**Note on Video Display on GitHub:** Standard Markdown on platforms like GitHub does not support embedding video previews directly using HTML `<video>` tags for security reasons. While the HTML tag works in local Markdown previews (like in VS Code), it will likely be stripped or ignored when viewed on the GitHub website.

To view the demonstration video on GitHub, you can:

*   **Download the video**: Click on the `Sample.mp4` file in the repository file list to download and play it locally.
*   **Link to a hosting service**: If you upload the video to a service like YouTube or Vimeo, you can embed it using their provided embed code or a standard Markdown link to the video page.
*   **Provide a direct link**: The current README includes a direct link to the file: `[Sample.mp4](Sample.mp4)`. Users can click this link to download or view the video depending on their browser settings.

## Other Information

*   **Base Model**: The project uses the standard `gpt2` model from the Hugging Face `transformers` library.
*   **Training Data**: The model was fine-tuned on a custom dataset of American singers' song lyrics.
*   **Output Directory**: The fine-tuned model and tokenizer are saved to the `fine_tuned_gpt2_lyrics` directory.

## Conclusion

This fine-tuned GPT-2 model represents a significant step in the realm of automated lyric generation. We hope you find this project useful and inspiring for your own creative endeavors. Feel free to experiment with the model and generate your own unique song lyrics!

For any questions or feedback, please feel free to reach out. Happy lyric generating!