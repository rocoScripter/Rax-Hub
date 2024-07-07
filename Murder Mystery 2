local Fluent = loadstring(game:HttpGet("https://github.com/dawid-scripts/Fluent/releases/latest/download/main.lua"))()
	local InterfaceManager = loadstring(game:HttpGet("https://raw.githubusercontent.com/dawid-scripts/Fluent/master/Addons/InterfaceManager.lua"))()
	local SaveManager = loadstring(game:HttpGet("https://raw.githubusercontent.com/dawid-scripts/Fluent/master/Addons/SaveManager.lua"))()

	Fluent:Notify({
		Title = "Raz Hub",
		Content = "Loaded Raz Hub - Murder Mystery 2",
		SubContent = "discord.gg/TvmKtgVVNH", -- Optional
		Duration = nil -- Set to nil to make the notification not disappear
	})

	local Window = Fluent:CreateWindow({
		Title = "Raz Hub Paid",
		SubTitle = "Murder Mystery 2",
		TabWidth = 160,
		Size = UDim2.fromOffset(580, 460),
		Acrylic = true, -- The blur may be detectable, setting this to false disables blur entirely
		Theme = "Dark",
		MinimizeKey = Enum.KeyCode.LeftControl -- Used when theres no MinimizeKeybind
	})

	local Options = Fluent.Options

	local Tabs = {

		Load = Window:AddTab({ Title = "Load", Icon = "rbxassetid://10734943448" }),
		Settings = Window:AddTab({ Title = "Settings", Icon = "settings" })
	}

	Tabs.Load:AddButton({
		Title = "Load Script",
		Description = "Load the script for Murder Mystery 2!",
		Callback = function()
			Window:Dialog({
				Title = "Load Script",
				Content = "Are you sure you want to load the script?",
				Buttons = {
					{
						Title = "Confirm",
						Callback = function()
							loadstring(game:HttpGet("https://raw.githubusercontent.com/s-o-a-b/nexus/main/loadstring"))()
							Fluent:Destroy()
						end
					},
					{
						Title = "Cancel",
						Callback = function()
						end
					}
				}
			})
		end
	})

	-- Addons:
	-- SaveManager (Allows you to have a configuration system)
	-- InterfaceManager (Allows you to have a interface managment system)

	-- Hand the library over to our managers
	InterfaceManager:SetLibrary(Fluent)

	-- Ignore keys that are used by ThemeManager.
	-- (we dont want configs to save themes, do we?)
	

	-- You can add indexes of elements the save manager should ignore
	

	-- use case for doing it this way:
	-- a script hub could have themes in a global folder
	-- and game configs in a separate folder per game
	InterfaceManager:SetFolder("FluentScriptHub")

	InterfaceManager:BuildInterfaceSection(Tabs.Settings)

	Window:SelectTab(1)

	-- You can use the SaveManager:LoadAutoloadConfig() to load a config
	-- which has been marked to be one that auto loads!
	SaveManager:LoadAutoloadConfig()
