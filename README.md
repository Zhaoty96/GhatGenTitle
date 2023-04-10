# Run GhatGenTitle

1. Install dependencies

```bash
pip install -r requirements.txt
```

2. Download model weights

```bash
cd llama-model/
wget https://agi.gpt4.org/llama/LLaMA/tokenizer.model -O ./tokenizer.model
wget https://agi.gpt4.org/llama/LLaMA/tokenizer_checklist.chk -O ./tokenizer_checklist.chk
wget https://agi.gpt4.org/llama/LLaMA/7B/consolidated.00.pth -O ./consolidated.00.pth
wget https://agi.gpt4.org/llama/LLaMA/7B/params.json -O ./params.json
wget https://agi.gpt4.org/llama/LLaMA/7B/checklist.chk -O ./checklist.chk
cd ../lora-model/
wget https://github.com/WangRongsheng/ChatGenTitle/releases/download/LLaMa-Lora-7B-cs-6-new-app/LLaMa-Lora-7B-cs-6-new-app.zip
```

3. Convert llama weights to hf

```bash
python convert_llama_weights_to_hf.py \
    --input_dir llama-model \
    --model_size 7B \
    --output_dir llama-model
```

4. Run

```bash
python app.py
```

5. Open `127.0.0.1:7860` in browser
