<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  
</head>
<body>

  <h1>🔍 Simple Attention Mechanism Demo</h1>

  <p>This notebook demonstrates a basic <strong>self-attention mechanism</strong> using NumPy — a core idea behind Transformer-based models like BERT and GPT.</p>

  <div class="highlight">
    <strong>👨‍💻 Skills covered:</strong><br>
    - Embedding representation<br>
    - Query, Key, and Value matrix generation<br>
    - Attention score calculation using dot product
  </div>

  <h2>📁 Structure</h2>
  <ul>
    <li><code>tok_*</code> — Example token vectors (Virat, Cricket, England)</li>
    <li><code>w_*</code> — Random weight matrices for Q, K, and V</li>
    <li><code>np.dot()</code> — Used for computing transformed vectors and similarity scores</li>
  </ul>

  <h2>🚀 How to Run</h2>
  <ol>
    <li>Make sure you have Python & NumPy installed</li>
    <li>Clone or download this notebook</li>
    <li>Run the notebook in Jupyter or any Python IDE</li>
  </ol>

  <h2>📈 Output Example</h2>
  <p>You'll see printed embeddings, weight matrices, and attention similarity scores between tokens like:</p>
  <pre>
Query for Cricket: [1.56 ...]
Key for Virat:     [5.10 ...]
Dot Product Score: 20.72
  </pre>

  <h2>📬 Feedback or Ideas?</h2>
  <p>Found it useful or have suggestions? Feel free to <a href="https://github.com/your-repo-url">contribute or raise an issue</a>.</p>

</body>
</html>
