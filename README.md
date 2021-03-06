# doomgeon
The latest craze in GaaS (Gaming as a Service)

Explore a new map with every character, of variable size and dangers, as well as rewards!

Available locally, in order to run this make sure you have python3 installed.  Download this repository to your environment, navigate to the doomgeon directory, and enter in the following command: flask\Scripts\python run.py (windows only).  For mac/linux, you should be able to simply use run.py, but YMMV.

NB: I was able to run this successfully as a downloaded package in a cloned repo on my original system, but have issues with python on my secondary.  If there are issues around starting it up, please refer to these references (they were used exclusively in setting up the original environment):
https://pypi.python.org/pypi/virtualenv
https://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-i-hello-world

Required packages:
flask
numpy
flask_sqlalchemy

Supported endpoints:
  Adventure begins!:
    /quest/start
    Required input: JSON {"player": {"name": "<PLAYER_NAME>"}}
    Example:
      curl -i -H "Content-Type: application/json" -X POST -d '{"player": {"name": "<PLAYER_NAME>"}}' http://127.0.0.1:5000/quest/start
  
  Adventure Ends:
    /quest/end
    Required input: JSON {"player": {"name": "<PLAYER_NAME>"}}
    Example: 
      curl -i -H "Content-Type: application/json" -X DELETE -d '{"player": {"name": "<PLAYER_NAME>"}}' http://127.0.0.1:5000/quest/end
  
  Player Status:
    /player/status/<PLAYER_NAME>
    Example: 
      curl -X GET http://127.0.0.1:5000/player/status/<PLAYER_NAME>
      
  Move Within the Dungeon:
    /player/move/<ROOM_ID>
    Required input: JSON {"player": {"name": "<PLAYER_NAME>"}}
    Example: 
      curl -i -H "Content-Type: application/json" -X GET -d '{"player": {"name": "<PLAYER_NAME>"}}' http://127.0.0.1:5000/player/move/<ROOM_ID>
      
 Enjoy your adventuring!
 
 TODO: Multilevel support, ability to interact with room events, and much much more!
    
