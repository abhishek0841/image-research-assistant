# image-research-assistant
# 🧠 Multimodal Image Research Assistant  
### (MCP + Gemini Vision + Wikipedia Retrieval)

This project implements a **multimodal research assistant** that can identify visual content in an image and automatically retrieve historical or contextual information from Wikipedia.

Instead of manually performing:
- reverse image search
- opening multiple tabs
- copy–pasting keywords
- reading through long articles

the assistant performs the entire workflow through a **single image upload**.

---

## 🚀 Key Highlights

✅ Multimodal AI (Vision + Text Retrieval)  
✅ Model Context Protocol (MCP) orchestration  
✅ Agent-style pipeline with specialized servers  
✅ Real-world research use case  
✅ Modular & extensible architecture  
✅ Gemini Vision integration  
✅ Wikipedia knowledge extraction  

---

## 🧩 Architecture

<img width="785" height="474" alt="image" src="https://github.com/user-attachments/assets/35824a73-1a0a-4987-a5f1-5d2965da398d" />


---

## 🛠 System Overview

The system consists of three main components:

### 🔹 VisualAnalysisServer
- Sends the uploaded image to **Gemini Vision**
- Generates a natural-language description of the image

### 🔹 WikipediaResearchServer
- Takes the description text
- Retrieves relevant Wikipedia articles
- Returns summaries and links

### 🔹 MCP Client (Orchestrator)
- Coordinates both servers
- Handles the full reasoning flow
- Delivers final results to the user

---

## 🔁 Workflow

1. User uploads an image  
2. VisualAnalysisServer analyzes it using Gemini Vision  
3. Generates descriptive text  
4. MCP Client sends description to WikipediaResearchServer  
5. Relevant Wikipedia information is retrieved  
6. Final results are displayed to the user  

---
Input: Please analyze the image at "/usercode/pyramid.jpeg" and give me its detailed description.
<img width="757" height="498" alt="image" src="https://github.com/user-attachments/assets/508943d2-3d67-4567-a9bb-e3d313ad1417" />

The agent will autonomously determine that it must first call the load_image_from_path tool and then use that output to call the get_image_description tool. The final output from our running application will look like this:

<img width="1404" height="411" alt="image" src="https://github.com/user-attachments/assets/c0d383e9-8f61-4173-8343-e0dd1f9bb9bf" />

As we can see, our VisualAnalysisServer has successfully analyzed the image and generated a detailed, accurate description. The agent correctly identified the image as depicting the Pyramids of Giza in Egypt.

By successfully building the VisualAnalysisServer, we have done more than just implement a tool; we have given our agent a new sense. We have demonstrated how a complex, multimodal process can be neatly encapsulated within a self-contained MCP server, exposing its powerful capabilities through a simple, standardized interface. The text description our server now produces is not the final answer: it is the crucial piece of evidence that will fuel the next stage of our agent’s research. We have successfully translated pixels into meaning, setting the stage for transforming that meaning into knowledge.

