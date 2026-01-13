### Overview
- **Purpose**: The macro allows users to generate and modify CAD models in FreeCAD through natural language inputs. It leverages the OpenAI API to interpret user instructions and produce corresponding Python code for CAD operations.
- **License**: Released under the MIT License, allowing free use, modification, and distribution with proper credit.

### Setup Instructions
1. **Load the Macro**: Import the macro into FreeCAD.
2. **API Key Configuration**: Set your OpenAI API key as an environment variable (`OPENAI_API_KEY`).
3. **Run the Macro**: Execute the macro within FreeCAD to interact with the AI chat interface.

### Key Components

#### 1. **OpenAI Integration**
- Utilizes the `openai` library to communicate with the OpenAI API.
- Configures the API client using an environment variable for the API key.

#### 2. **User Interface**
- **ChatDock Class**: A dockable widget in FreeCAD's GUI that provides a chat interface for user interaction.
  - **Chat Display**: Shows conversation history with AI responses.
  - **Input Field**: Allows users to enter natural language commands.
  - **Buttons**: Includes options to send messages, add reference images, and undo/redo actions.

#### 3. **AI Interaction**
- **OpenAIWorker Class**: Handles asynchronous communication with the OpenAI API.
  - Processes user input and system messages to generate AI responses.
  - Supports both text-based and image-enhanced queries.

#### 4. **Code Execution**
- Extracts Python code blocks from AI responses and executes them in FreeCAD.
- Manages transactions in FreeCAD to apply or rollback changes based on AI-generated code.

#### 5. **Object Management**
- Maintains a registry of FreeCAD objects to track their states and properties.
- Provides functions to build system messages that inform the AI about the current state of the CAD model.

#### 6. **Error Handling**
- Captures and displays errors encountered during AI communication or code execution.

### Usage Flow
- Users describe desired CAD operations in natural language.
- The macro sends these descriptions to the OpenAI API, which returns Python code.
- The code is executed in FreeCAD to create or modify CAD models accordingly.
- Users can view and manage the results through the chat interface, including undoing or redoing actions.
