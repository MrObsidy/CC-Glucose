--Glucose graphics API by the Nethercraft Team
--MrObsidy24, CCPlayer3D


--Local Variables
local authors = {"MrObsidy24", "CCPlayer3D"}

local animations = true
local applicationObject = {}
local ribbon = {}
local ribbonInstance = {}
local ribbonContents = {}
local termObject = {}
local preloadedRibbonData = {
	[1] = "",
	[2] = "",
	[3] = "",
	[4] = "",
	[5] = ""
}

--Global Variables
GLC_VERSION = 1.1 --Increased by one since Animations and this field were added
GLC_MINCOSV = 1.7

--Local Functions

--Global Functions
function init(title, author)
  if not term.isColor() or monochromeMode then
    colors.orange = colors.lightGray
    colors.orange = colors.lightGray
    colors.lightBlue = colors.lightGray
	colors.yellow = colors.lightGray
	colors.lime = colors.lightGray
	colors.pink = colors.lightGray
	colors.cyan = colors.gray
	colors.purple = colors.gray
	colors.blue = colors.gray
	colors.brown = colors.gray
	colors.green = colors.gray
	colors.red = colors.gray
	
	colours.orange = colours.lightGrey
 colours.orange = colours.lightGrey
 colours.lightBlue = colours.lightGrey
	colours.yellow = colours.lightGrey
	colours.lime = colours.lightGrey
	colours.pink = colours.lightGrey
	colours.cyan = colours.Grey
	colours.purple = colours.Grey
	colours.blue = colours.Grey
	colours.brown = colours.Grey
	colours.green = colours.Grey
	colours.red = colours.Grey
  end
  applicationObject.author = author
  applicationObject.title = title
  applicationObject.applicationBaseColor = colors.white  
  ribbon.baseColor = colors.gray
  ribbon.entryBackgroundColor = colors.gray 	--This should always be the same as baseColor, otherwise it looks odd. -MrObsidy24
  ribbon.textColor = colors.white
  ribbon.openColor = colors.lightGray
  ribbon.contentTextColor = colors.black
  ribbon.lastXPos = 1
  ribbon.previousRibbon = nil
  term.setBackgroundColor(applicationObject.applicationBaseColor)
  term.clear()
  term.setCursorPos(1,1)
  term.setBackgroundColor(ribbon.baseColor)
  term.setTextColor(ribbon.textColor)
  term.clearLine()
  term.setCursorPos(1,1)
  term.write(applicationObject.title)
  term.setCursorPos(1,2)
  term.clearLine()
  termObject.X, termObject.Y = term.getSize()
end

function terminate()
term.clear()
term.setBackgroundColor(colors.black)
term.setTextColor(colors.white)
term.clear()
term.setCursorPos(1,1)
end

function makeEdgeButton(letter, line)
  term.setBackgroundColor(ribbon.baseColor)
  term.setCursorPos(termObject.X, line)
  term.write(letter)
end

function createMenuBand()
  applicationObject.menuBand = true
  ribbon.isRibbon = true
end

function setRibbonBaseColor(color)
  ribbon.baseColor = color
end

function setRibbonContentTextColor(color)
	ribbon.contentTextColor = color
end

function setRibbonAttribute(internalName, attribute, value)
  ribbonInstance[internalName][attribute] = value
end

function toggleAnimations()
  if animations == true then
    animations = false
  else
    animations = true
  end
end

function setRibbonTextColor(color)
  ribbon.textColor = color
end

function setLastRibbon(ribbonentered)
  ribbon.previousRibbon = ribbonentered
end

function setRibbonBaseColor(color)
  ribbon.baseColor = color
end

function getRibbonAttribute(internalName, attribute)
  return ribbonInstance[internalName][attribute]
end

function makeRibbonEntry(title, internalName)
 	term.setCursorPos(ribbon.lastXPos, 2)
  term.setBackgroundColor(ribbon.baseColor)
  term.setTextColor(ribbon.textColor)
  ribbonInstance[internalName] = {["created"] = true}
  setRibbonAttribute(internalName, "baseColor", ribbon.baseColor)
  setRibbonAttribute(internalName, "textColor", ribbon.textColor)
  setRibbonAttribute(internalName, "openColor", ribbon.openColor)
  setRibbonAttribute(internalName, "startPosition", ribbon.lastXPos)
  setRibbonAttribute(internalName, "ribbonTitle", title)
  setRibbonAttribute(internalName, "endPosition", (ribbon.lastXPos + string.len(title)) - 1)
  setRibbonAttribute(internalName, "ribbonData", preloadedRibbonData) --only to prevent erroring
  setRibbonAttribute(internalName, "ribbonIcon", {}) --only to prevent erroring
  write(title)
  ribbon.lastXPos = ribbon.lastXPos + string.len(title)
end

function drawRibbonContents(ribbonEnt)
	  term.setCursorPos(1, 3)
	  term.clearLine()
	  term.setCursorPos(1, 4)
	  term.clearLine()
	  term.setCursorPos(1, 5)
	  term.clearLine()
	  term.setCursorPos(1, 6)
	  term.clearLine()
	  term.setCursorPos(1, 7)
	  term.clearLine()
  local oldColor = term.getTextColor()
  
  term.setTextColor(ribbon.contentTextColor)
  local ribbonData = getRibbonAttribute(ribbonEnt, "ribbonData")
  
   term.setCursorPos(1, 3)
   term.write(ribbonData[1])
   term.setCursorPos(1,4)
   term.write(ribbonData[2])
   term.setCursorPos(1,5)
   term.write(ribbonData[3])
   term.setCursorPos(1,6)
   term.write(ribbonData[4])
   term.setCursorPos(1,7)
   term.write(ribbonData[5])
   
  term.setTextColor(oldColor)
   
end

-- function drawIcon(ribbonEnt)
	-- local oldBGColor = term.getBackgroundColor()
	-- local oldTextColor = term.getTextColor()
	
		-- local instance = ribbonInstance[ribbonEnt]
		-- local iconDataTable = instance["ribbonIcon"]
		
		-- for k, v in pairs(iconDat aTable) do
			-- term.setCursorPos(iconDataTable[], 6)
		-- end
	
	-- term.setBackgroundColor(oldBGColor)
	-- term.setBackgroundColor(oldTextColor)
-- end

function addIcon(ribbonEnt, iconTable)
	local ribbonInstanceEnt = ribbonInstance[ribbonEnt]
	
	if not ribbonInstanceEnt["ribbonIcon"][ribbonBasePos] then
		ribbonInstanceEnt["ribbonIcon"][ribbonBasePos] = 1
	end
	
	previousPos = ribbonInstanceEnt["ribbonIcon"]["ribbonEndPos"]
	
	ribbonInstanceEnt["ribbonIcon"]["ribbonBasePos"] = previousPos + 1
end

function addRibbonContent(ribbonEnt, content)
	setRibbonAttribute(ribbonEnt, "ribbonData", content)
	drawRibbonContents(ribbonEnt)
end

function openRibbon(ribbonEnt)
  
  if ribbon.previousRibbon then
    local previousBG = getRibbonAttribute(ribbon.previousRibbon, "baseColor")
	local previousTC = getRibbonAttribute(ribbon.previousRibbon, "textColor")
    local previousPos = getRibbonAttribute(ribbon.previousRibbon, "startPosition")
    local previousTitle = getRibbonAttribute(ribbon.previousRibbon, "ribbonTitle")
    term.setBackgroundColor(previousBG)
	term.setTextColor(previousTC)
    term.setCursorPos(previousPos, 2)
    write(previousTitle)
  end
  
  local ribbonData = ribbonInstance[ribbonEnt]
  term.setTextColor(ribbonData.textColor)
  term.setBackgroundColor(ribbonData.openColor)
  term.setCursorPos(ribbonData.startPosition, 2)
  write(ribbonData.ribbonTitle)
  drawRibbonContents(ribbonEnt)
  ribbon.previousRibbon = ribbonEnt
end

local function fillLineWithCharacters(line, character)
	local x, y = term.getSize()
	
	term.setCursorPos(1, line)
	
	local posCount = 0
	repeat
		write(character)
		posCount = posCount + 1
	until posCount > x
end

function createDialogBox(text, title)
	local _X, _Y = term.getSize()
	local dialogheight = 0
	for k, v in pairs(text) do
		dialogheight = dialogheight + 1
	end
	dialogheight = dialogheight + 2 --for the OK button and the title
	local lineCounter = math.floor((_Y - dialogheight)/ 2)
	local ribbonBaseColor = ribbon.baseColor
	local ribbonTextColor = ribbon.textColor
	
	term.setBackgroundColor(ribbon.baseColor)
	term.setTextColor(ribbon.textColor)
	
	term.setCursorPos(1, lineCounter - 1)
	term.clearLine()
	fillLineWithCharacters( lineCounter  - 1, "=")
	writeCentered(title, lineCounter - 1)
	for k, v in pairs(text) do
		term.setCursorPos(1, lineCounter)
		term.clearLine()
		writeCentered(v, lineCounter)
		lineCounter = lineCounter + 1
	end
	term.setCursorPos(1, lineCounter)
	term.clearLine()
	term.setBackgroundColor(colors.red)
	local start, stop = writeCentered("OK", lineCounter)
	term.setCursorPos(1, lineCounter + 1)
	term.setBackgroundColor(ribbonBaseColor)
	term.clearLine()
	
	term.setBackgroundColor(applicationObject.applicationBaseColor)
	
	term.setTextColor(colors.black)
	while true do
		local event, button, x, y = os.pullEvent("mouse_click")
		if button == 1 and x >= start and x <= stop and y == lineCounter then
			term.setCursorPos(1,8)
			local sizeX, sizeY = term.getSize()
			local currentLine = 8
			repeat
				term.setCursorPos(1, currentLine)
				term.clearLine()
				currentLine = currentLine + 1
			until currentLine > sizeY
			break
		end
	end
	
	openRibbon(ribbon.previousRibbon)
	
	ribbon.baseColor = ribbonBaseColor
	ribbon.textColor = ribbonTextColor
	
end

function writeCentered(text, yCoord)
	local x, y = term.getSize()
	local xPos = math.floor((x - string.len(text)) / 2) + 1
	term.setCursorPos(xPos, yCoord)
	write(text)
	return xPos, xPos + string.len(text) + 1
end
