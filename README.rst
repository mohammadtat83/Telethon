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


Doing stuff
-----------

.. code:: python

  print(client.get_me().stringify())

  client.send_message('username', 'Hello! Talking to you from Telethon')
  client.send_file('username', '/home/myself/Pictures/holidays.jpg')

  client.download_profile_photo('me')
  messages = client.get_messages('username')
  client.download_media(messages[0])


Next steps
----------

Do you like how Telethon looks? Check out
`Read The Docs <http://telethon.rtfd.io/>`_
for a more in-depth explanation, with examples,
troubleshooting issues, and more useful information.
