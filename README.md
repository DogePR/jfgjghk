local VLib = loadstring(game:HttpGet("https://raw.githubusercontent.com/vep1032/VepStuff/main/VL"))()

local s = VLib:Window("VAPE MENU", "V1", " ")

local ss = s:Tab("Farm")

ss:Button("Seller",function()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-6.94805383682251, -9.375523567199707, -22.614315032958984)
end)

ss:Button("Bank",function()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-245.68240356445312, 5.445750713348389, 96.60964965820312)
end)

ss:Button("IceBox",function()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(600.5029907226562, 3.2499794960021973, -181.62806701660156)
end)


 ss:Button("Server Hop",function()

	local x = {}
	for _, v in ipairs(game:GetService("HttpService"):JSONDecode(game:HttpGetAsync("https://games.roblox.com/v1/games/" .. game.PlaceId .. "/servers/Public?sortOrder=Asc&limit=100")).data) do
		if type(v) == "table" and v.maxPlayers > v.playing and v.id ~= game.JobId then
			x[#x + 1] = v.id
		end
	end
	if #x > 0 then
		game:GetService("TeleportService"):TeleportToPlaceInstance(game.PlaceId, x[math.random(1, #x)])
end
end)
