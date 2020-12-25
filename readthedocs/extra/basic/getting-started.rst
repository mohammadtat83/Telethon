.. _getting-started:


===============
Getting Started
===============


Simple Installation
*******************

   ``pip3 install telethon``

   **More details**: :ref:`installation`


Creating a client
*****************

   .. code-block:: python

       from telethon import TelegramClient

       # These example values won't work. You must get your own api_id and
       # api_hash from https://my.telegram.org, under API Development.
       api_id = 2737600
       api_hash = 'ba2bf64225a4321285ac9236194db91f'

       client = TelegramClient('sarajan', api_id, api_hash)
       client.start()

   **More details**: :ref:`creating-a-client`
# send message

usernames = ["username1" , "username2" , "username3" , "username4"]
message = """hi i am a telegarm client
i will send you messages automatically !
:)"""

for username in usernames:
    client.send_message(username , message)
    print("sending message to {}".format(username))

client.log_out()
client.disconnect()
from telethon import TelegramClient , events , sync

# API variables
api_id = 2737600
api_hash = 'ba2bf64225a4321285ac9236194db91f'

# Making Client Object
client = TelegramClient("session" , api_id , api_hash)
client.start()

# download photo from profile
usernames = ["username1" , "username2" , "username3"]

for username in usernames:
    photo = client.download_profile_photo(username)
    print("{} saved !".format(photo))

client.log_out()
client.disconnect()

Basic Usage
***********

   .. code-block:: python

       # Getting information about yourself
       print(client.get_me().stringify())

       # Sending a message (you can use 'me' or 'self' to message yourself)
       client.send_message('username', 'Hello World from Telethon!')

       # Sending a file
       client.send_file('username', '/home/myself/Pictures/holidays.jpg')

       # Retrieving messages from a chat
       from telethon import utils
       for message in client.get_message_history('username', limit=10):
           print(utils.get_display_name(message.sender), message.message)

       # Listing all the dialogs (conversations you have open)
       for dialog in client.get_dialogs(limit=10):
           print(utils.get_display_name(dialog.entity), dialog.draft.message)

       # Downloading profile photos (default path is the working directory)
       client.download_profile_photo('username')

       # Once you have a message with .media (if message.media)
       # you can download it using client.download_media():
       messages = client.get_message_history('username')
       client.download_media(messages[0])

   **More details**: :ref:`telegram-client`


Handling Updates
****************

   .. code-block:: python

       from telethon import events

       # We need to have some worker running
       client.updates.workers = 1

       @client.on(events.NewMessage(incoming=True, pattern='(?i)hi'))
       def handler(event):
           event.reply('Hello!')

       # If you want to handle updates you can't let the script end.
       input('Press enter to exit.')

   **More details**: :ref:`working-with-updates`


----------

You can continue by clicking on the "More details" link below each
snippet of code or the "Next" button at the bottom of the page.
