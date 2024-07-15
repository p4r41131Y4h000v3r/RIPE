Ioannis Konstas' WHOIS IP Information Script

This Bash script is designed to automate the process of retrieving WHOIS information for IP addresses from the RIPE NCC (Réseaux IP Européens Network Coordination Centre) database. It provides a user-friendly interface for querying IP addresses and includes error handling and helpful features.

Script Structure and Functions

The script is organized into several functions to enhance modularity and maintainability:

clear_screen():

Clears the terminal screen for a clean display.
print_header():

Clears the screen and prints the script's header, which includes your name and the database being queried. This header is consistently displayed throughout the script's execution.
center_text():

Takes a text string as input and prints it centered on the terminal screen. This is used to format the output visually.
draw_box():

Takes a multi-line string (content) as input.
Determines the length of the longest line in the content.
Dynamically calculates the width of a box to fit the content with padding.
Draws a box around the content using ASCII characters, ensuring it scales to the content's size.
run_whois():

Takes an IP address as input.
Queries the RIPE NCC database using the whois command.
Extracts relevant information (inetnum, address, netname, description, country) from the output using awk.
Prints the formatted WHOIS information within a dynamically sized box.
Prompts the user to press Enter to continue or 'e' to exit.
Exits the script if the user chooses 'e'.
prompt_for_ip():

Prints the script header.
Displays a box with instructions for entering an IP address or using options ('e' to exit, 'example', or 'help').
Prompts the user to enter an IP address.
Main Script Logic

Welcome Message: Greets the user to the script.

Initial Prompt: Calls prompt_for_ip to get the first IP address from the user.

Main Loop:

Enters an infinite while true loop.

Input Handling: Uses a case statement to handle different user inputs:

help: Prints detailed instructions.
example: Demonstrates a sample query using 8.8.8.8.
e: Exits the script.
Valid IP Address: Calls run_whois to perform the query and display the results.
Invalid IP Address: Prints an error message.
Exit Check: Checks if the user chose to exit within run_whois. If not, it calls prompt_for_ip again to get the next IP address. Otherwise, it breaks the loop.

Key Features

User-Friendly: Provides clear instructions, helpful options, and a visually appealing output.
Dynamic Box: The box that encloses the WHOIS information adjusts its size based on the content, ensuring a neat presentation.
Consistent Header: The header with your name is displayed after each action, providing a consistent user experience.
Error Handling: Checks for valid IP address format and provides appropriate feedback.
Exit Option: Allows the user to exit the script gracefully at any time.
