## Steps
### This is the question-and-answer llama2 finetune model creation task. For that, I use free datasets from Huggingface, not generated data using an OpenAI API key. I couldn't get the free trial one. after preprocessing those data and fine-tuning the model

**All codes and model data can find using**  [Google Drive Link](https://drive.google.com/drive/folders/1EnpgWq-RJ5cHyuUzRRYl9eBIh4dQTfyI?usp=sharing)

1. **Requirements- To Install**

   - !pip install -q pyarrow==14.0.1
   - !pip install -q fsspec==2024.6.1
   - !pip install -q requests==2.31.0
   - !pip install -q datasets huggingface_hub
   - !pip install -q peft
   - !pip install -q accelerate==0.21.0 peft==0.4.0 bitsandbytes==0.40.2 transformers==4.31.0 trl==0.4.7

3. **Download Datasets from Huggingface** - [Datasets](https://huggingface.co/datasets/timdettmers/openassistant-guanaco)

   - Then preprocess the dataset according to the Llama2-specific prompt template
   - Convert the dataset to a pandas DataFrame - a type of ```.jsonl``` and store data
   - Split ```train_dataset```

4. **Model training**

   - Download ```NousResearch/Llama-2-7b-chat-hf``` by Huggingface as a base model
   - Load tokenizer and model with QLoRA configuration
   - Load LoRA configuration
   - Set training parameters
   - Set supervised fine-tuning parameters
   - Train model

5. **Model Testing**
     - Run text generation pipeline with our next model
     - the Save the Train model
