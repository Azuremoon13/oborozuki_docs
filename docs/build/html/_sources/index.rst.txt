.. Oborozuki documentation master file, created by
   sphinx-quickstart on Fri Jun 17 20:16:51 2022.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to Oborozuki's documentation!
=====================================

**Oborozuki** is a Python project utilising twitchio and twitch's API to run 
channel moderation, with custom command capability and some fun mini-games.
This project has just been released in closed beta, if you wish to 
participate, please head to `Oborozuki's channel <https://www.twitch.tv/oborozuki13/>`_ and type
!invite into the channels chat!

.. note::

   This project is under active development and is in EARLY stages of a beta
   
.. toctree::
   :maxdepth: 2
   :caption: Contents:

Standard commands:
==================
| **Here is some usage on the standard commands to config this bot in your channel**
| !command add/remove/edit/option - you can use this to modify the custom commands in your channel
|     - add : use this to add a command, required args: !command add {name} {command response} I.E. !command add !hi hello o/ !
|     - remove : use this to remove a command, required args: !command remove {name} I.E. !command remove !hi
|     - edit : use this to edit a command, required args: !command edit {name} {command response} I.E. !command edit !hi hello i am new here o/ !
|     - option : use this to adjust the options for the command, there are 3 options to adjust; user level and global/user cooldowns (level=E,S,V,M,B)(GCD=0)(UCD=0) required args: !command option {name} {option} I.E. !command option !hi GCD=5

| !quiet - use this to disable all custom commands in this channel
|     - if you follow this command with a 1 this will disable the commands I.E. !quiet 1
|     - if you follow this command with a 0 this will enable the commands I.E. !quiet 0

| !links - use this to enable link protection in the channel
|     - if you follow this command with a 1 this will enable the link protection I.E. !links 1
|     - if you follow this command with a 0 this will disable the link protection I.E. !links 0

| !banned - use this to ban a certain word from your channel.
|     - follow this command with the word you wish to ban I.E. !banned poo
|     - can only ban one word at a time

| !emotes - use this to enable emotes only mode - (useful for mobile moders)

| !emotesoff - use this to disable emotes only mode - (useful for mobile moders)

| !clear - This will purge the chat of all messages. (blocked by BTTV) - (useful for mobile moders)


Custom command args:
====================

| #~~~ user name ~~~#
| This is to get the name of the user that invoked the command:
| 'I am ${user}, hello' = I am obrozuki13, hello


| #~~~ game ~~~#
| This is to return the current game of the channel:
| 'We currently are playing ${game}' = We currently are playing Valorant.

| #~~~ target name ~~~#
| This is to return the target in a given command:
| '${user} hugs ${target}' = obrozuki13 hugs azure

| notes: 
| - if there is no user specified for the target, it will self target the user. 
| - if there is no tag from twitch using '@' it will default to the first word after the command invoke, conversely if there is a tag it will use this even if its not first word.

| #~~~ url fetch ~~~#
| This is to run a api fetch from a url and return it in plain text.
| 'we currently are ${url.https://api.kyroskoh.xyz/valorant/v1/mmr/eu/x/x}' = we currently are Radiant - 66rr

| #~~~ count ~~~#
| This is used to create a count for a certain thing, this will increment the counter each time it is invoked:
| we have died ${count deaths} times = we have died 13 times

| Notes:
| - this doesnt just have to me a random name, you can use other custom args in this to create unique counters

| #~~~ getcount ~~~#
| This is used to get a count for a certain thing:
| we have died ${getcount deaths} times = we have died 13 times

| #~~~ rand user ~~~#
| This will return a random user in the chat.
| Here is a random user.. ${randuser} you have won! = Here is a random user.. Azure you have won!

| notes: 
| - this will also include any bots in your chat.

| #~~~ rand number ~~~#
| this will return a random number between the 2 numbers you specify.
| 'I am ${randnum.0-110}% lit today' = I am 69% lit today.

| #~~~ word ~~~#
| coming soon...