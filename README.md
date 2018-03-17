-----------------------------------------------------------------------------------------
-- Created by: Aayman Shameem
-- Created on: Feb 26 2018
--
-- how to calculate the area of a trapezoid
-- 
-----------------------------------------------------------------------------------------
display.setDefault( "background", 0, 0, 0 )


-- showing what A, B and H are in the formula
local AOfTrapezoidDisplay = display.newText( "Length --> ", display.contentCenterX - 850, display.contentCenterY, native.systemFont, 100 )
AOfTrapezoidDisplay:setFillColor( 1, 1, 1 )

local BOfTrapezoidDisplay = display.newText( "Width --> ", display.contentCenterX - 850, display.contentCenterY + 150, native.systemFont, 100 )
BOfTrapezoidDisplay:setFillColor( 1, 1, 1 )

local HOfTrapezoidDisplay = display.newText( "Height --> ", display.contentCenterX - 850, display.contentCenterY + 300, native.systemFont, 100 )
HOfTrapezoidDisplay:setFillColor( 1, 1, 1 )


-- the text fields of the three inputs
local AOfTrapezoidTextField = native.newTextField( display.contentCenterX - 300, display.contentCenterY, 675, 150 )
AOfTrapezoidTextField.id = "AInput"

local BOfTrapezoidTextField = native.newTextField( display.contentCenterX - 300, display.contentCenterY + 150, 675, 150 )
BOfTrapezoidTextField.id = "BInput"

local HOfTrapezoidTextField = native.newTextField( display.contentCenterX - 300, display.contentCenterY + 300, 675, 150 )
HOfTrapezoidTextField.id = "HInput"

local areaOfTrapezoidTextField = display.newText( "Answer: ", display.contentCenterX + 300, display.contentCenterY + 100, native.systemFont, 100 )
areaOfTrapezoidTextField.id = "AreatextField"
areaOfTrapezoidTextField:setFillColor( 0, 1, 0 )

-- the enter button
local calculateButton = display.newImageRect( "./assets/sprites/enterButton.png", 458, 277 )
calculateButton.x = display.contentCenterX + 400
calculateButton.y = display.contentCenterY - 200
calculateButton.id = "calculate button"
 
local function trapezoidArea( event )
    -- this function calculates the area of a trapezoid given the length, width and height of the trapezoid

    local clear = display.newRect(display.contentCenterX + 570, display.contentCenterY + 100, 240, 160)
 	clear: setFillColor( 0, 0, 0 )

 	local clear1 = display.newRect(display.contentCenterX, display.contentCenterY + 488, 3000, 200)
 	clear1: setFillColor( 0, 0, 0 )

    local AOfTrapezoid = tonumber(AOfTrapezoidTextField.text)
    	if AOfTrapezoid == nil then
    		local errorMessage1 = display.newText( "VALUE MUST BE GREATER THAN OR EQUAL TO 1", display.contentCenterX, display.contentCenterY + 488, native.systemFont, 100 )
    		return false
    	end

    local BOfTrapezoid = tonumber(BOfTrapezoidTextField.text)
    	if BOfTrapezoid == nil then
    		local errorMessage1 = display.newText( "VALUE MUST BE GREATER THAN OR EQUAL TO 1", display.contentCenterX, display.contentCenterY + 488, native.systemFont, 100 )
    		return false
    	end

    local HOfTrapezoid = tonumber(HOfTrapezoidTextField.text)
    	if HOfTrapezoid == nil then
    		local errorMessage1 = display.newText( "VALUE MUST BE GREATER THAN OR EQUAL TO 1", display.contentCenterX, display.contentCenterY + 488, native.systemFont, 100 )
    		return false
    	end

    local areaOfTrapezoid

	

	-- This will calculate the area of the trapezoid with the user's input
    local areaOfTrapezoid = (AOfTrapezoid + BOfTrapezoid) / 2 * HOfTrapezoid
    
    -- displaying the answer in correct format
    local areaOfTrapezoidAnswer = display.newText( (areaOfTrapezoid), display.contentCenterX + 570, display.contentCenterY + 100, native.systemFont, 100 )
    areaOfTrapezoidAnswer:setFillColor( 1, 1, 1 )

    

    return true
end

calculateButton:addEventListener( "touch", trapezoidArea )
