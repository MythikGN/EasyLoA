# EasyLoA

EasyLoA is similar in function to EasyUO. You can write basic/complex scripts to automate tedious parts of the game.

The Script Parser at the moment only supports C#, though additional languages can be added fairly easiliy if there is demand, ie Lua etc.
Full intellisense is provided via RosylnPad.

#### Properties
        TargetRequestType CURTARGREQTYPE;
        string CHARNAME;
        ulong CHARID;
        bool ISMOUNTED;
        string CHARLOC;
        bool INCOMBAT;
        double CURSPEED;
        string LASTANIM;
        bool ISWALKING;
        string GAMESTATE;
        ulong CURTARGET;
        ulong LASTTARGETID;
        ulong MOUSEOVERID;
        string LastScriptCommand;
        Dictionary<string,ValHolder> StatsSkills = new Dictionary<string,ValHolder>();
        
Stats and skill names vary depending on server, so current/max etc can be accessed via the dictionary where the key is the stat/skills name.
        

#### Functions:
      SendScriptCommand(string cmd, ulong targetid = 0) // send any / command
      UseHotbarAction(int index) // use one of your numbered hotkeys
      Move(float x, float y, float z, bool blocking = false)
      PickupObject(ulong objectid) // pickup item
      DropItem(ulong objectid, ulong targetid  = 0, float x = 0, float y =0, float z = 0) // drop item onto item
      TargetLocation(float x, float y, float z)
      TargetOject(ulong id)
      WaitForTarget(TargetRequestType targetType, TimeSpan timeout)

#### Still to add

      Journal and System messages
      Dynamic Windows
      Weight / Other char stats.
      
### Server Admins
When a script is ran in EasyLoA, the server is sent a custom command "/EasyLoA {Version}"
It's at your discretion as to how to handle this command server side. You could dissconnect the client, send a warning to not macro afk or what ever you want.

