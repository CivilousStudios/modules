--// CoderCrazy, 2020

local System = {}
local Order = {"Opening", "People", "Task", "Location", "Reason"}
local Sounds = {
	["Opening"] = {
		5429842387,
		5429843776
	},
	["People"] = {
		-- Crew
		5429848669,
		5429850831,
		5429852218,
		5429853341,
		5429854224,
		5429855225,
		-- Scientists
		5429856564,
		5429858608,
		5429859460,
		5429861640,
		5429862771,
		5429863819,
		5429864891,
		5429865840,
		5429867939,
		5429869108,
		5429870361,
		5429871480,
		5429873354,
		5429874436,
		5429876647,
		5429877706,
		5429879000,
		5429879977,
		
		-- Security
		5429881454,
		5429882503,
		5429883504,
		5429884896,
		5429885847,
		5429887651
	},
	["Task"] = {
		5429891438,
		5429892948
	},
	["Location"] = {
		-- Crew
		5429896557,
		5429898165,
		5429899204,
		5429900207,
		5429902485,
		5429904371,
		
		-- Scientist
		5429906433,
		5429909084,
		5429910266,
		5429913397,
		5429914781,
		5429915956,
		5429917201,
		
		-- Security
		5429920328,
		5429925422,
		5429926689,
		5429928967,
		5429930124,
		5429932350
	},
	["Reason"] = {
		-- Crew
		5429939533,
		5429941643,
		5429942780,
		5429943851,
		5429944923,
		5429946075,
		5429947336,
		
		-- Scientist
		5429948628,
		
		-- Security
		5429950445,
		5429952082,
		5429953412
	}
}

local DEBUG = game:GetService("ReplicatedStorage"):WaitForChild("SCPCB_DEBUG", 2)

System.GetSounds = function(Dictionary, Single)
	if not Dictionary then
		return Sounds
	elseif tostring(Dictionary) and Sounds[tostring(Dictionary)] then
		return Single and Sounds[tostring(Dictionary)] or Sounds[tostring(Dictionary)][math.random(1, #Sounds[tostring(Dictionary)])]
	else
		return nil
	end
end

System.CreateAnnouncement = function()
	local Delta = {}
	for i = 1, #Order do
		Delta[i] = System.GetSounds(Order[i])
	end
	if DEBUG	then DEBUG:FireAllClients(Delta) end
	return Delta
end

System.CreateAndPlayAnnouncement = function(Sound)
	Sound.SoundId = "rbxassetid://5430139055"
	Sound:Play()
	local Announcement = System.CreateAnnouncement()
	Sound.Ended:Wait() wait(.1)
	for i = 1, #Announcement do
		Sound.SoundId = "rbxassetid://" .. Announcement[i]
		Sound:Play()
		Sound.Ended:Wait()
		wait(.2)
	end
	return true
end

return System
