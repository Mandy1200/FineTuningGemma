<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
</head>
<body>

  <h1>🔍 Self-Attention Mechanism Demonstration</h1>

  <p>This section illustrates a simplified self-attention mechanism using NumPy, a foundational concept behind transformer-based models such as BERT and GPT.</p>

  <h3>📘 Key Concepts</h3>
  <ul>
    <li>Token embedding representation</li>
    <li>Query, Key, and Value matrix computation</li>
    <li>Attention scoring using dot product</li>
  </ul>

  <h3>⚙️ How to Run</h3>
  <ol>
    <li>Ensure Python and NumPy are installed</li>
    <li>Open the notebook in Jupyter or any Python IDE</li>
    <li>Review intermediate outputs including embeddings and similarity scores</li>
  </ol>

  <hr>

  <h1>🚀 Fine-Tuning <code>gemma-2b</code> with LoRA</h1>

  <p>This section demonstrates efficient fine-tuning of Google’s <code>gemma-2b</code> model using Low-Rank Adaptation (LoRA), along with quantization techniques to optimize memory usage and performance.</p>

  <h3>🧰 Technology Stack</h3>
  <ul>
    <li><strong>Frameworks:</strong> PyTorch, Hugging Face Transformers, PEFT, Accelerate</li>
    <li><strong>Optimization:</strong> BitsAndBytes (8-bit & 4-bit quantization)</li>
    <li><strong>Environment:</strong> Google Colab with GPU (CUDA 12.4)</li>
  </ul>

  <h3>📦 Installation</h3>
  <pre>
pip install torch==2.5.1+cu124 torchvision==0.20.1+cu124 torchaudio==2.5.1+cu124 \
  --index-url https://download.pytorch.org/whl/cu124

pip install bitsandbytes==0.46.0 transformers==4.48.3 accelerate==1.3.0 datasets peft
  </pre>

  <h3>🔐 Authentication</h3>
  <pre>
from huggingface_hub import login
login("your-hf-token", add_to_git_credential=True)
  </pre>

  <h3>🧠 Model Loading Options</h3>
  <p>Supports full precision, 8-bit, and 4-bit quantized loading.</p>

  <strong>8-bit Example:</strong>
  <pre>
quant_config = BitsAndBytesConfig(load_in_8bit=True)

base_model = AutoModelForCausalLM.from_pretrained(
  "google/gemma-2b",
  quantization_config=quant_config,
  device_map="auto"
)
  </pre>

  <strong>4-bit Example:</strong>
  <pre>
quant_config = BitsAndBytesConfig(
  load_in_4bit=True,
  bnb_4bit_use_double_quant=True,
  bnb_4bit_compute_dtype=torch.bfloat16,
  bnb_4bit_quant_type="nf4"
)
  </pre>

  <h3>📌 LoRA Configuration</h3>
  <pre>
TARGET_MODULES = ["q_proj", "k_proj", "v_proj", "o_proj"]
LORA_R = 32
LORA_ALPHA = 64
  </pre>

  <h3>📉 Memory Footprint Overview</h3>
  <ul>
    <li><strong>Full Precision:</strong> ~10 GB</li>
    <li><strong>8-bit Quantized:</strong> ~3 GB</li>
    <li><strong>4-bit Quantized:</strong> ~2 GB</li>
    <li><strong>LoRA Weights Only:</strong> ~1.3 MB</li>
  </ul>

  <h3>📐 Parameter Summary</h3>
  <p>Each projection layer includes:</p>
  <pre>
(4096 × 32) + (4096 × 32) per direction
Total Parameters: 33,554,432
Estimated Size: ~1.34 MB
  </pre>

  <h3>⚠️ Runtime Considerations</h3>
  <ul>
    <li>Package installations must be repeated after each Colab reset</li>
    <li>Model download may vary based on network speed</li>
    <li><code>device_map="auto"</code> ensures GPU usage when available</li>
  </ul>

  <h3>📬 Feedback & Contributions</h3>
  <p>Suggestions or improvements are welcome. Please visit the <a href="https://github.com/your-repo-url">GitHub repository</a> to contribute or raise issues.</p>

</body>
</html>
