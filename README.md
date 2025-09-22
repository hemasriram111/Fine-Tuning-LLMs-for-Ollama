# Fine-Tuning LLMs for Ollama

This project demonstrates how to **fine-tune open-source language models** with custom data and then run them locally using **[Ollama](https://ollama.ai/)**.  

It uses **Google Colab** for training (leveraging free GPUs) and integrates the trained model into Ollama for local inference.  

---

## 🔑 What is Fine-Tuning?
Fine-tuning takes a pre-trained model (like LLaMA, Mistral, etc.) and adapts it to your **specific task or domain**.  

Examples:  
- Extracting structured data from HTML  
- Customer support conversations  
- Domain-specific knowledge (legal, medical, etc.)  

### Benefits
- Requires fewer examples than training from scratch  
- Produces specialized models for better accuracy in your use case  
- Can reduce costs by using smaller models  

---

## ⚙️ Workflow
1. **Prepare Data**  
   - Collect examples in JSON format (input → expected output).  
   - Example: extracting product name, price, category from HTML snippets.  

2. **Set Up Training in Google Colab**  
   - Upload your dataset.  
   - Install dependencies.  
   - Load a base model (small models recommended for speed).  
   - Preprocess data into prompt → output format.  

3. **Fine-Tune with LoRA Adapters**  
   - Apply adapters to enable efficient training.  
   - Use the `SFTTrainer` to run training.  

4. **Test the Model in Colab**  
   - Run inference on sample prompts.  
   - Verify outputs match expected format.  

5. **Export the Model**  
   - Save the fine-tuned model in `.gguf` format.  
   - Download the file to your local machine.  

6. **Integrate with Ollama**  
   - Create a **Model File** (defines base model, parameters, and templates).  
   - Use:
     ```bash
     ollama create -f ModelFile <model-name>
     ```
   - Run with:
     ```bash
     ollama run <model-name>
     ```

---

## 📂 Example Files
- **Dataset JSON** – input/output pairs for fine-tuning  
- **Training Notebook** – step-by-step Colab script  
- **Model File** – Ollama configuration for your trained model  

---

## 🚀 Quick Start
1. Clone/download the project.  
2. Open the provided notebook in **Google Colab**.  
3. Upload your dataset and run training.  
4. Export the `.gguf` model file.  
5. Create a Model File in Ollama.  
6. Run your fine-tuned model locally!  

---

## ⚠️ Notes
- Use a **small dataset + small model** for quick experiments.  
- More data = better results (but longer training).  
- Fine-tuned models are **better at your task, but worse at general tasks**.  

---
