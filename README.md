# Redz Lib V5
## Load the Library
```lua
local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/realredz/RedzLibV5/main/Source.lua"))()
```
### Library's Functions
```lua
-- Get Icon
-- For get icons, see lib/Icons.lua
Library:GetIcon("Home")

-- Set Theme
Library:SetTheme("Purple") -- See lib/Themes.lua

-- Set Window's Scale
Library:SetScale(1)
```

## Window
### Create a Window
```lua
local Window = Library:MakeWindow({
    Title = "redz Library V5",
    SubTitle = "by : redz9999",
    SaveFolder = false -- Save Configs on Player's Device
})
```
### Window's Functions
```lua
-- Close Window (with user confirmation)
Window:CloseBtn()
-- Minimize Window (with user confirmation)
Window:MinimizeBtn()

-- Minimize Window
Window:Minimize()

-- Set New Title and/or Subtitle
Window:Set("New Title", "New Subtitle")

-- Select Tab
Window:SelectTab("Tab Name")
```

## Tab
### Create a Tab
```lua
local Tab = Window:MakeTab({
    Title = "Tab",
    Icon = "Home" -- See lib/Icons.lua
})
```
### Tab's Functions
```lua
-- Disable Tab
Tab:Disable()

-- Enable Tab
Tab:Enable()

-- Set Tab's Visibility
Tab:Visible(false)

-- Destroy Tab
Tab:Destroy()
```

## Section
### Create a Section
```lua
local Section = Tab:AddSection({
    Title = "Section"
})
```
### Section's Functions
```lua
-- Set Section's Visibility
Section:Visible(false)

-- Destroy Section
Section:Destroy()

-- Set Section's New Title/Name
Section:Set("New Name")
```

## Paragraph
### Create a Paragraph
```lua
local Paragraph = Tab:AddParagraph({
    Title = "Paragraph",
    Text = "This is a Paragraph"
})
```
### Paragraph's Functions
```lua
-- Set Paragraph's Visibility
Paragraph:Visible(false)

-- Destroy Paragraph
Paragraph:Destroy()

-- Set Paragraph's New Title And Text
Paragraph:Set("New Title", "New Text")

-- OR

Paragraph:SetTitle("New Title")
Paragraph:SetDesc("New Text")
```

## Button
### Create a Button
```lua
local Button = Tab:AddButton({
    Title = "Button",
    Desc = "Button's Description", -- Optional
    Callback = function ()
        print("Button Clicked")
    end
})
```
### Button's Functions
```lua
-- Set Button's Visibility
Button:Visible(false)

-- Destroy Button
Button:Destroy()

-- Set Button's New Callback
Button:Callback(function ()

end)

-- Set Button's New Title And Description
Button:Set("New Title", "New Description")
```

## Toggle
### Create a Toggle
```lua
local Toggle = Tab:AddToggle({
    Title = "Toggle",
    Desc = "Toggle's Description", -- Optional
    Callback = function (Value)
        print("Toggle State Change", Value)
    end,
    Default = false, -- Default State
    Flag = false
})
```
### Toggle's Functions
```lua
-- Set Toggle's Visibility
Toggle:Visible(false)

-- Destroy Toggle
Toggle:Destroy()

-- Set Toggle's New Callback
Toggle:Callback(function (Value)

end)

-- Set Toggle's New Title And Description
Toggle:Set("New Title", "New Description")
```

## Dropdown
### Create a Dropdown
```lua
local Dropdown = Tab:AddDropdown({
    Title = "Dropdown",
    Desc = "Dropdown's Description", -- Optional
    Options = {"One", "Two", "Three"},
    Callback = function (Value)
        print("Dropdown Item Select", Value)
    end,
    Default = "One", -- Default Value
    Flag = false,
    MultiSelect = false -- Optional
})
```
### Dropdown's Functions
```lua
-- Set Dropdown's Visibility
Dropdown:Visible(false)

-- Destroy Dropdown
Dropdown:Destroy()

-- Set Dropdown's New Callback
Dropdown:Callback(function (Value)

end)

-- Add new option(s) to Dropdown
Dropdown:Add("Four", "Five", "Six") -- And can add more values!

-- Remove a option from Dropdown
Dropdown:Remove("One")

-- Select option from Dropdown
Dropdown:Select("Three")

-- Add new option(s) V2
Dropdown:Set({"Seven", "Eight"})

-- OR Add new option(s) and clear Dropdown

Dropdown:Set({"Seven", "Eight"}, true)
```

## Slider
### Create a Slider
```lua
local Slider = Tab:AddSlider({
    Title = "Slider",
    Desc = "Slider's Description", -- Optional
    Min = 0,
    Max = 100,
    Increase = 1,
    Callback = function (Value)
        print("Slider Value Change", Value)
    end,
    Flag = false,
    Default = 50
})
```
### Slider's Functions
```lua
-- Set Slider's New Title And Description
Slider:Set("New Title", "New Description")

-- Set Slider's New Callback
Slider:Callback(function (Value)

end)

-- Set Slider's Visibility
Slider:Visible(false)

-- Destroy Slider
Slider:Destroy()
```

## Text Box (Input)
### Create a Text Box
```lua
local TextBox = Tab:AddTextBox({
    Title = "Text Box",
    Desc = "Text Box's Description", -- Optional
    Default = "", -- Default Text Box's Value
    PlaceholderText = "< Input >",
    ClearText = false, -- Optional, Clear old Input on focus
    Callback = function (Value)
        print("TextBox Value Change", Value)
    end
})
```
### TextBox's Functions
```lua
-- Set TextBox's Visibility
TextBox:Visible(false)

-- Destroy TextBox
TextBox:Destroy()
```

## Extra
### Add Discord Invite
```lua
local DiscordInvite = Tab:AddDiscordInvite({
    Title = "Discord",
    Desc = "Join in our discord server", -- Optional
    Logo = "", -- Optional, Icon
    Invite = "" -- Discord Invite's Link
})
```
#### Discord Invite's Functions
```lua
-- Destroy Discord Invite
DiscordInvite:Destroy()

-- Set Discord Invite's Visibility
DiscordInvite:Visible(false)
```

### Minimize Button
#### Add Minimize Button
```lua
Window:AddMinimizeButton({
    Corner = {
        CornerRadius = UDim.new(0.5, 0)
    },
    Stroke = {},
    Button = {
        --[[
            Only accepts Image ID not Decal ID.
            If you use Decal ID, try to convert to Image ID
        --]]
        Image = "rbxassetid://15298567397"
    }
})
```

### Dialog
#### Make a Dialog
```lua
local Dialog = Window:Dialog({
    Title = "Example Dialog",
    Text = "This is a example dialog",
    Options = {} -- Add Buttons directly, see below (Dialog's Functions)
})
```
#### Dialog's Functions
```lua
-- Add button to Dialog
Dialog:Button({
    Title = "Close",
    Callback = function ()
        print("Dialog's Close Button")
    end
})

-- Close the Dialog
Dialog:Close()
```
