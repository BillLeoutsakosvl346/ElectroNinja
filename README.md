# ElectroNinja - Electrical Engineer Agent

ElectroNinja is an interactive circuit design assistant built with Python and PyQt5. It leverages OpenAI’s language models and a FAISS-based vector database to help electrical engineers generate LTSpice schematic files (.asc) from natural language requests. The tool provides a chat interface for design assistance, a code editor for circuit generation, and an integrated circuit preview pane.

---

## Features

- **Interactive GUI**  
  A PyQt5-based interface featuring:
  - A chat panel for conversation and design advice.
  - A code editor for displaying and editing LTSpice schematic code.
  - A circuit preview pane for visualizing the generated circuit.

- **LLM-Powered Circuit Generation**  
  Uses OpenAI models (e.g., `o3-mini` for circuit code generation and `gpt-4o-mini` for chat responses) to produce valid LTSpice (.asc) files from your circuit design instructions.

- **Semantic Example Retrieval**  
  Utilizes a FAISS vector database to store and retrieve circuit examples, which guide the code generation process.

- **LTSpice Integration**  
  Supports compiling, saving, and launching circuit designs in LTSpice directly from the application.

- **Image Analysis**  
  Includes a vision module that can analyze circuit images to verify whether they match the user’s requirements.

---

## Project Structure

- **ingest_examples.py**  
  Ingests and indexes circuit examples into the FAISS vector database.

- **main.py**  
  The primary application entry point that integrates the chat manager, vector database, and GUI components.

- **retrieve.py**  
  A command-line tool to perform semantic searches over stored circuit examples.

- **chat_manager.py**  
  Manages LLM interactions for generating both LTSpice circuit code and friendly chat responses.

- **vector_db.py**  
  Handles document embedding and storage using a FAISS index for semantic search.

- **vision.py**  
  Analyzes circuit images by interfacing with an OpenAI model that supports image inputs.

- **circuit_saver.py**  
  Automates saving and exporting circuit designs from LTSpice, including converting schematics to PNG.

- **chat_panel.py**  
  Implements a scrollable chat panel for displaying conversation history with adaptive bubble sizing.

---

## Prerequisites

### LTSpice Installation

ElectroNinja integrates directly with LTSpice for simulation and previewing circuit designs. Before running ElectroNinja, ensure LTSpice is installed on your system. Follow the tutorial below for downloading and installing LTSpice.

---

### LTSpice Download & Installation Tutorial

1. **Visit the LTSpice Download Page**  
   Open your web browser and navigate to the [Analog Devices LTSpice page](https://www.analog.com/en/design-center/design-tools-and-calculators/ltspice-simulator.html).

2. **Download the Installer**  
   - Scroll down to find the download link for LTSpice.
   - Click on the appropriate installer for your operating system (Windows or macOS).
   - Save the installer file to your computer.

3. **Install LTSpice**  
   - **For Windows Users:**  
     Double-click the downloaded `.exe` file and follow the on-screen instructions.
   - **For macOS Users:**  
     Open the downloaded `.dmg` file, drag the LTSpice application to your Applications folder, and then launch it.

4. **Configure ElectroNinja**  
   Once LTSpice is installed, update the `ltspice_path` variable in the following files to point to your LTSpice executable:
   - `circuit_saver.py`
   - `middle_panel.py` (located under the `gui` directory)

---

## Installation

1. **Clone the Repository**

   ```bash
   git clone https://github.com/yourusername/electroninja.git
   cd electroninja

 
