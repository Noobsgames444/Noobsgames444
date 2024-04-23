import discord
import os

intents = discord.Intents.default()
intents.messages = True

client = discord.Client(intents=intents)

@client.event
async def on_ready():
    print('Logged in as {0.user}'.format(client))

@client.event
async def on_message(message):
    # Prevent the bot from responding to itself
    if message.author == client.user:
        return
    
    # Your chatbot logic here
    response = generate_response(message.content)
    
    # Send the response
    await message.channel.send(response)

def generate_response(input_text):
    # Your chatbot's response generation logic here
    # For simplicity, let's just echo the input
    return input_text

client.run(os.environ['DISCORD_TOKEN'])  # Make sure to set DISCORD_TOKEN as an environment variable
import discord
import os

intents = discord.Intents.default()
intents.messages = True
intents.guilds = True  # Enable guild events to handle DMs

client = discord.Client(intents=intents)

@client.event
async def on_ready():
    print('Logged in as {0.user}'.format(client))

@client.event
async def on_message(message):
    # Prevent the bot from responding to itself
    if message.author == client.user:
        return
    
    # Check if the message was sent in a guild (server) or a DM
    if isinstance(message.channel, discord.DMChannel):
        # Respond to DMs
        response = generate_response(message.content)
        await message.channel.send(response)
    else:
        # Your chatbot logic for server messages
        # For simplicity, let's just echo the input
        response = generate_response(message.content)
        await message.channel.send(response)

def generate_response(input_text):
    # Your chatbot's response generation logic here
    # For simplicity, let's just echo the input
    return input_text

client.run(os.environ['DISCORD_TOKEN'])  # Make sure to set DISCORD_TOKEN as an environment variable

