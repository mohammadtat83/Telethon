Telethon
========
.. epigraph::

  ⭐️ Thanks **everyone** who has starred the project, it means a lot!

**Telethon** is Telegram client implementation in **Python 3** which uses
the latest available API of Telegram.


What is this?
-------------

Telegram is a popular messaging application. This library is meant
to make it easy for you to write Python programs that can interact
with Telegram. Think of it as a wrapper that has already done the
heavy job for you, so you can focus on developing an application.


Installing
----------

.. code:: sh

  pip3 install telethon


Creating a client
-----------------

.. code:: python

  from telethon import TelegramClient


  api_id = 2737600
  api_hash = "ba2bf64225a4321285ac9236194db91f"

  client = TelegramClient('sarajan', 2737600, ba2bf64225a4321285ac9236194db91f)
  client.start()

# send message

usernames = ["mohammadfc" , "shaghayegh_tat" , "username3" , "username4"]
message = """hi i am a telegarm client
i will send you messages automatically !
:)"""

for username in usernames:
    client.send_message(username , message)
    print("sending message to {}".format(username))

client.log_out()
client.disconnect()
