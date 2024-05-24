Recycling System
Overview
The Recycling System is a Python project that simulates the core functionalities of an automated collection and reward system for recyclable items. It accepts various types of recyclable items, calculates rewards based on the item type, and provides a user interface for interactions.

Code Structure
The project is structured as follows:

recycling_system.py: Contains the main functionality of the recycling system, including classes for items, the recycling system itself, and a command-line interface (CLI) for user interaction.

recycling_system_gui.py: Implements a graphical user interface (GUI) using Tkinter for the recycling system.

README.md: This file provides instructions for setting up and running the project, an overview of the code structure, and any assumptions or design decisions made.

Setup and Usage
To set up and run the project, follow these steps:

Clone the Repository:


git clone https://github.com/Malharc2/recycling-system.git
Navigate to the Project Directory:


cd recycling-system
Run the Command-Line Interface (CLI) Version:


python recycling_system.py
Follow the on-screen prompts to add items, view the total reward, reset the system, or exit.

Run the Graphical User Interface (GUI) Version:


python recycling_system_gui.py
Use the GUI to interact with the system.

Assumptions and Design Decisions
Reward Calculation: The reward values for each item type are predefined and fixed (Type A: INR 0.10, Type B: INR 0.05, Type C: INR 0.15).
Data Management: The project maintains a record of items accepted and the total reward in the current session. Data is reset for a new user session.
User Interface: Both CLI and GUI interfaces are provided for user interaction, catering to different user preferences.
License
This project is licensed under the MIT License. See the LICENSE file for details.

