import discord
from discord.ext import commands

client = commands.Bot(command_prefix= "!")
client = commands.Bot(command_prefix= "?")

@client.event
async def on_ready():
    print('Bot has loaded')

@client.command()
async def on_message(message):
    if message.author == client.user:
        return
    if message.content.startswith("hello"):
        await message.channel.send("Hey, whats up?")

@client.command()
async def server(ctx):
    name = ctx.guild.name
    description = ctx.guild.description

    owner = str(ctx.guild.owner)
    id = str(ctx.guild.id)
    region = str(ctx.guild.region)
    memberCount = str(ctx.guild.member_count)

    icon = ctx.guild.icon_url

    embed = discord.Embed(
        title=name + "Server Information",
        description=description,
        color=discord.Color.blue()
    )
    embed.set_thumbnail(url=icon)
    embed.add_field(name="Owner", value=owner, inline=True)
    embed.add_field(name="Server ID", value=id, inline=True)
    embed.add_field(name="Region", value=region, inline=True)
    embed.add_field(name="Member Count", value=memberCount, inline=True)

    await ctx.send(embed=embed)