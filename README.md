# Autogen.projects-
a. Classes and Methods
config_list_from_json autogen

This function loads a configuration list from an environment variable or a given JSON file.
Setting parameters
environment_or_file: an environment variable holding the configuration or a string giving the name of the JSON file.
Goal: It makes the agent configuration settings reusable and adaptable.
autogen.HelpingAgent

Represents an artificial intelligence (AI) assistant agent that can communicate with users or other agents to carry out tasks or respond to inquiries.
Setting parameters
name: A string representing the agent's name, "Assistant" in this case.
llm_config: A dictionary holding the language model's configuration options. These options are stored in the config_list parameter.
Goal: Sets up the assistant with the appropriate settings and capabilities to carry out duties.
UserProxyAgent autogen

Functions as an intermediary between users and the helper agent, mimicking user interactions. It can run programming and manage human input.
Setting parameters
name: The string "user" serves as the proxy's name.
human_input_mode: Indicates the frequency at which human input is necessary. The value "NEVER" indicates that execution requires no human intervention.
code_execution_config: Code execution configuration dictionary:
work_dir: With "coding" selected, this is the working directory for executing code.
use_docker: Set to False to indicate that Docker should not be used for code execution.
Its purpose is to set up the user proxy's interactions with the assistance and to manage the execution of code.
Using user_proxy.start_chat

Starts a conversation between the AssistantAgent and the UserProxyAgent.
Setting parameters
assistant: The agent acting as an assistant throughout the discussion.

message: Tell the assistant to "Plot a chart of META and TESLA stock price change." This is the first message or job.
Goal: Initiates a discussion and gives the helper instructions on how to complete a particular assignment.
b. Logic Configuration Loading:

Using config_list_from_json, the script loads configuration settings from "OAI_CONFIG_LIST.json" at the start. The settings included in this configuration list are required for configuring the agents.
Initialization of the agent:

The loaded configuration list is then used to initialise an AssistantAgent with the name "Assistant".
Concurrently, a UserProxyAgent with the name "user" is established, equipped with particular configurations that regulate the code execution environment and input mode.
Starting a Conversation:

Initiating a conversation, the UserProxyAgent sends a message to the AssistantAgent requesting a plot of changes in stock prices for Tesla and META.
c. Expected Outcome

The script is supposed to cause the UserProxyAgent to speak with the AssistantAgent and request that it create a chart that displays the fluctuations in the stock prices of Tesla and META. It is expected of the assistant to handle the request, obtain the required information, and produce the chart in the prescribed manner.

Answer Classes and Methods: The script loads configurations using config_list_from_json and creates a conversational framework using AssistantAgent and UserProxyAgent. The agents' conversation starts with the initiate_chat method.
Logic: After loading configuration parameters and initialising the agents with them, the script uses the UserProxyAgent to ask the AssistantAgent for a chart showing changes in stock prices.
Anticipated Result: A chart illustrating the fluctuations in META's stock prices ought to be created by the AssistantAgent.
