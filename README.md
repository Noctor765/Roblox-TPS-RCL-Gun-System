# Roblox-TPS-RCL-Gun-System

Structure of game: {

Workspace:
    "Bullets" -> an empty Folder.

ReplicatedStorage:
    "GunSystem" -> Folder
         "RemoteEvents" -> Folder which is a child to the GunSystem folder.
             "Draw&Damage" -> RemoteEvent which is a child under the RemoteEvents folder.
             "Weld" -> RemoteEvent which is a child under the RemoteEvents folder.

ServerScriptService:
    "GunServer" -> Script (Or commonly known as a server script)

StarterPlayer -> StarterPlayerScripts:
    "GunClient" -> LocalScript (Or commonly known as a client script)
          "GunTemplate" -> ModuleScript (This is just for typecasting/typechecking usage but is needed)

StarterGui:
    "AmmoGUI" -> Just a normal ScreenGui (MAKE SURE WHEN YOU ARE DONE CUSTOMISING YOUR GUI TO SET THE ENABLED PROPERTY OF THE "AmmoGUI" to false which means the tick should not be there in order for it to work with the gunclient code)
        "Frame" -> Think of it as a background for your textlabel and make sure it is called Frame and the classtype is a Frame to. (This is a child to the AmmoGUI of course).
            "Ammo" -> TextLabel classtype which is a child of Frame and design it however you want it (Again make sure after you designed you're GUI to set the Enabled property of the AmmoGUI to false).

StarterPack:
    Not needed but if you want to test it out i guess put the guntool under the starterpack service.

}

Structure of GunTool: {
    (IMPORTANT: Make sure these properties are set to false under the GunTool (RequiresHandle = false | CanBeDropped = false) ALSO IT MUST HAVE THE BOOLEAN ATTRIBUTE NAMED "Gun" (Make the boolean attribute is set to true))
    "GunSettings" -> ModuleScript (self-explanatory from the name) Child to the GunTool.
    "GunModel" -> Model classtype and child to the GunTool aswell. This has all the guntools make sure to use the weldconstraint to weld the part0 and part1 as the parts of the gunparts and the handle (Make sure the handle is the parent of these weldconstraints).
    "Handle" -> Part classtype meant to be invinsible and positioned at the guns trigger location also a child of the GunTool. (MAKE SURE TO ADD THE "firstCFrame" BOOLEAN ATTRIBUTE TO THE HANDLE AS false.)
        "FirePart" -> Part classtype meant to be invinsible and positioned at the guns end of barrel location also a child of the Handle (Make sure to use a weldconstraint to weld this to the handle)
        "GunShot" -> Sound classtype which is a child of the Handle
        "GunReload" -> Sound classtype which is a child of the Handle

    IMPORTANT: THE HANDLE AND FIREPART MUST HAVE THESE PROPERTIES BELOW: {
    CanCollide = false,
    Anchored = false,
    CanTouch = false,
    CanQuery = false,
    Massless = true,
    AudioCanCollide = false,
    CastShadow = false
    
    Rest as default.
    }

    The properties are mainly for the tool to work as desired and optimisation purposes.
}
