# Recycling System

## Project Description

The Recycling System is a basic Python project that simulates the core functionalities of an automated collection and reward system for recyclable items. It supports accepting various types of recyclable items, calculating rewards based on the item type, and maintaining a simple user interface for interactions.

## Features

- Item Acceptance: Accepts different types of recyclable items (Type A, Type B, and Type C).
- Reward Calculation: Each item type has a predefined reward value:
  - Type A: INR 0.10
  - Type B: INR 0.05
  - Type C: INR 0.15
- User Interface: Provides both a command-line interface (CLI) and a graphical user interface (GUI) using Tkinter.
- Data Management: Maintains a record of the items accepted and the total reward in the current session, and allows resetting of the data for a new user session.

## Requirements

- Python 3.x
- Tkinter (included with standard Python libraries)

## Installation

No special installation steps are required since Tkinter is included with Python. Ensure you have Python 3 installed on your system.

## Usage

1. Running the CLI Version:
   - Save the CLI code to a file, e.g., `recycling_system_cli.py`.
   - Run the script using Python:
     ```bash
     python recycling_system_cli.py
     ```
   - Follow the on-screen prompts to add items, view the total reward, reset the system, or exit.

2. Running the GUI Version:
   - Save the GUI code to a file, e.g., `recycling_system_gui.py`.
   - Run the script using Python:
     ```bash
     python recycling_system_gui.py
     ```
   - Use the GUI to add items, view the total reward, reset the system, or quit the application.

## Code Overview

### Item Class

```python
class Item:
    def __init__(self, item_type, reward):
        self.item_type = item_type
        self.reward = reward
Represents a recyclable item with a type and reward value.
RecyclingSystem Class
class RecyclingSystem:
    def __init__(self):
        self.items = []
        self.total_reward = 0.0
        self.item_rewards = {'A': 0.10, 'B': 0.05, 'C': 0.15}

    def add_item(self, item_type):
        if item_type in self.item_rewards:
            item = Item(item_type, self.item_rewards[item_type])
            self.items.append(item)
            self.total_reward += item.reward
            return f"Added item of type {item_type} with reward {item.reward} INR"
        else:
            return "Invalid item type. Please enter A, B, or C."

    def view_total_reward(self):
        return self.total_reward

    def reset_system(self):
        self.items = []
        self.total_reward = 0.0
        return "System has been reset."
class RecyclingSystem:
    def __init__(self):
        self.items = []
        self.total_reward = 0.0
        self.item_rewards = {'A': 0.10, 'B': 0.05, 'C': 0.15}

    def add_item(self, item_type):
        if item_type in self.item_rewards:
            item = Item(item_type, self.item_rewards[item_type])
            self.items.append(item)
            self.total_reward += item.reward
            return f"Added item of type {item_type} with reward {item.reward} INR"
        else:
            return "Invalid item type. Please enter A, B, or C."

    def view_total_reward(self):
        return self.total_reward

    def reset_system(self):
        self.items = []
        self.total_reward = 0.0
        return "System has been reset."
RecyclingSystem Class:
class RecyclingSystem:
    def __init__(self):
        self.items = []
        self.total_reward = 0.0
        self.item_rewards = {'A': 0.10, 'B': 0.05, 'C': 0.15}

    def add_item(self, item_type):
        if item_type in self.item_rewards:
            item = Item(item_type, self.item_rewards[item_type])
            self.items.append(item)
            self.total_reward += item.reward
            return f"Added item of type {item_type} with reward {item.reward} INR"
        else:
            return "Invalid item type. Please enter A, B, or C."

    def view_total_reward(self):
        return self.total_reward

    def reset_system(self):
        self.items = []
        self.total_reward = 0.0
        return "System has been reset."
Manages the collection of items and calculation of rewards. Contains methods to add items, view the total reward, and reset the system.

RecyclingSystemGUI Class:


class RecyclingSystemGUI:
    def __init__(self, root, system):
        self.root = root
        self.system = system
        self.root.title("Recycling System")
        self.create_widgets()
        
    def create_widgets(self):
        self.label = tk.Label(self.root, text="Enter item type (A, B, C):")
        self.label.pack(pady=5)
        self.entry = tk.Entry(self.root)
        self.entry.pack(pady=5)
        self.add_button = tk.Button(self.root, text="Add Item", command=self.add_item)
        self.add_button.pack(pady=5)
        self.view_button = tk.Button(self.root, text="View Total Reward", command=self.view_total_reward)
        self.view_button.pack(pady=5)
        self.reset_button = tk.Button(self.root, text="Reset System", command=self.reset_system)
        self.reset_button.pack(pady=5)
        self.quit_button = tk.Button(self.root, text="Quit", command=self.root.quit)
        self.quit_button.pack(pady=5)
        self.result_label = tk.Label(self.root, text="", fg="blue")
        self.result_label.pack(pady=5)

    def add_item(self):
        item_type = self.entry.get().upper().strip()
        result = self.system.add_item(item_type)
        self.result_label.config(text=result)
        self.entry.delete(0, tk.END)

    def view_total_reward(self):
        total_reward = self.system.view_total_reward()
        messagebox.showinfo("Total Reward", f"Total reward accumulated: {total_reward:.2f} INR")

    def reset_system(self):
        result = self.system.reset_system()
        self.result_label.config(text=result)

Manages the Tkinter-based GUI. Contains methods to create widgets and handle user interactions.


Main Function:


def main():
    root = tk.Tk()
    system = RecyclingSystem()
    app = RecyclingSystemGUI(root, system)
    root.mainloop()

if __name__ == "__main__":
    main()

Initializes the Tkinter root window and the recycling system, creates an instance of the RecyclingSystemGUI class, and starts the Tkinter main loop.

License
This project is licensed under the MIT License. See the LICENSE file for details.

Contributing
Contributions are welcome! Please feel free to submit a pull request or report issues.

Acknowledgments
Thanks to the Python community for providing comprehensive documentation and support.


