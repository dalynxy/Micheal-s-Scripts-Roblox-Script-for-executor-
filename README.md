# Micheal-s-Scripts-Roblox-Script-for-executor-

Welcome to Micheal's Scripts!
This is an Roblox Script for Roblox Executors (if they are still working due to Byfron anticheat update.)
This is still in beta but it's really small script.

You can also get it from my pastebin: https://pastebin.com/yL23jC4D

____________________________________________________________________
The whole script:

local Rayfield = loadstring(game:HttpGet('https://raw.githubusercontent.com/shlexware/Rayfield/main/source'))()
 
local Window = Rayfield:CreateWindow({
   Name = "Micheal_'s Scripts V1",
   LoadingTitle = "Still loading.",
   LoadingSubtitle = "by Micheal_",
   ConfigurationSaving = {
      Enabled = true,
      FolderName = nil, -- Create a custom folder for your hub/game
      FileName = "MichealsScripts"
   },
   Discord = {
      Enabled = false,
      Invite = "noinvitelink", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ABCD would be ABCD
      RememberJoins = true -- Set this to false to make them join the discord every time they load it up
   },
   KeySystem = true, -- Set this to true to use our key system
   KeySettings = {
      Title = "Micheal_'s Scripts V1",
      Subtitle = "Key System",
      Note = "Put the key or else you won't get into it.",
      FileName = "EntryPass", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
      SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
      GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
      Key = {"Keyy"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
   }
})
 
Rayfield:Notify({
   Title = "Welcome!",
   Content = "Welcome to Micheal_'s Scripts. Click okay!",
   Duration = 6.5,
   Image = 4483362458,
   Actions = { -- Notification Buttons
      Ignore = {
         Name = "Okay!",
         Callback = function()
         print("Someone used Micheal_'s Scripts | Join: .gg/gnbag6vb7H")
      end
   },
},
})
 
local Movement = Window:CreateTab("Movement", 4483362458) -- Title, Image
 
local Slider = Movement:CreateSlider({
   Name = "Walskpeed",
   Range = {16, 1000},
   Increment = 10,
   Suffix = "WalkSpeed",
   CurrentValue = 16,
   Flag = "Slider1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
       game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = Value
   end,
})
 
local Slider = Movement:CreateSlider({
   Name = "JumpPower",
   Range = {16, 500},
   Increment = 10,
   Suffix = "JumpPower",
   CurrentValue = 16,
   Flag = "Slider2", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
       game.Players.LocalPlayer.Character.Humanoid.JumpPower = Value
   end,
})
 
local Credits = Window:CreateTab("Credits", 4483362458) -- Title, Image
 
local Text1 = Credits:CreateLabel("Made by Micheal_ | .gg/gnbag6vb7H")
 
local Misc = Window:CreateTab("Misc", 4483362458) -- Title, Image
 
local Button = Misc:CreateButton({
   Name = "Destroy Gui",
   Callback = function()
       Rayfield:Destroy()
   end,
})
