<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
</head>
<body>
  <h1>🩺 Medical AI Chatbot — RAG Workflow in n8n</h1>

  <p>
    This project is a fully no-code, agentic <strong>Medical AI Chatbot</strong> built in <strong>n8n</strong>.  
    It uses <strong>Retrieval-Augmented Generation (RAG)</strong> to answer health-related questions with up-to-date, verified information.
  </p>

  <h2>✨ Key Features</h2>
  <ul>
    <li>Works as a conversational agent triggered by user chat messages.</li>
    <li>Uses the <strong>OpenRouter LLM</strong> (Mistral Mixtral-8x7B) to generate responses.</li>
    <li>Connects to a <strong>Pinecone Vector Store</strong> that indexes medical documents stored in Google Drive.</li>
    <li>Uploads new PDFs automatically from Google Drive and updates embeddings using Hugging Face or OpenAI.</li>
    <li>Follows strict system instructions to provide factual, clear, and patient-friendly answers.</li>
  </ul>

  <h2>📂 Files</h2>
  <p>
    <strong>Medical Assistant.json</strong><br/>
    The exported n8n workflow. Download and import it into your n8n instance.
  </p>

  <h2>⚙️ How It Works</h2>
  <ol>
    <li><strong>Chat Trigger:</strong> When a user sends a message, the workflow is triggered.</li>
    <li><strong>RAG Pipeline:</strong> 
      <ul>
        <li>The AI Agent uses a <strong>Simple Memory Buffer</strong> to maintain chat history context.</li>
        <li>Uses <strong>OpenRouter LLM</strong> to process the question with a strict system prompt for medical reliability.</li>
        <li>Retrieves facts from your <strong>Pinecone Vector Store</strong> connected to indexed medical PDFs.</li>
        <li>Uses <strong>Hugging Face</strong> or <strong>OpenAI</strong> embeddings to embed new documents.</li>
      </ul>
    </li>
    <li><strong>Document Management:</strong> 
      <ul>
        <li>A <strong>Google Drive Trigger</strong> detects new medical PDFs uploaded to your specified folder.</li>
        <li>New PDFs are downloaded, split into text chunks, embedded, and indexed in Pinecone automatically.</li>
      </ul>
    </li>
    <li><strong>Response:</strong> The agent replies to the user with clear, factual answers, suggesting consulting a doctor for serious issues.</li>
  </ol>

  <h2>🔑 Requirements</h2>
  <ul>
    <li>✅ <strong>n8n</strong> instance (cloud or self-hosted)</li>
    <li>✅ <strong>OpenRouter API key</strong> (for the LLM)</li>
    <li>✅ <strong>Hugging Face API key</strong> or <strong>OpenAI API key</strong> (for embeddings)</li>
    <li>✅ <strong>Pinecone API key</strong> (for vector storage)</li>
    <li>✅ <strong>Google Drive credentials</strong> for uploading medical PDFs</li>
  </ul>

  <h2>🚀 Setup Instructions</h2>
  <ol>
    <li>Download <code>Medical Assistant.json</code> from this repo.</li>
    <li>Login to your n8n workspace and go to <strong>Import Workflow</strong>.</li>
    <li>Upload the JSON file and click <strong>Import</strong>.</li>
    <li>Open the workflow, add your API credentials:
      <ul>
        <li><strong>OpenRouter</strong> for the LLM</li>
        <li><strong>Pinecone</strong> for vector storage</li>
        <li><strong>Hugging Face</strong> or <strong>OpenAI</strong> for embeddings</li>
        <li><strong>Google Drive OAuth</strong> for document uploads</li>
      </ul>
    </li>
    <li>Save and activate the workflow.</li>
    <li>Upload new medical PDFs to the connected Google Drive folder — they will be indexed automatically!</li>
    <li>Test by sending a chat message to your AI chatbot — get accurate, factual answers in real-time!</li>
  </ol>

  <h2>📚 References</h2>
  <ul>
    <li><a href="https://n8n.io/">n8n Docs</a></li>
    <li><a href="https://openrouter.ai/">OpenRouter</a></li>
    <li><a href="https://www.pinecone.io/">Pinecone</a></li>
    <li><a href="https://huggingface.co/">Hugging Face</a></li>
    <li><a href="https://www.openai.com/">OpenAI</a></li>
  </ul>

  <h2>✅ Notes</h2>
  <ul>
    <li>This chatbot only uses facts from your uploaded knowledge base — it will not hallucinate information.</li>
    <li>Always verify responses and consult a licensed physician for medical advice.</li>
  </ul>

  <p>💡 <strong>Tip:</strong> You can customize the system instructions to match your clinic or brand guidelines.</p>

  <p>🚀 Happy building your own RAG-based Medical AI Chatbot!</p>
</body>
</html>
