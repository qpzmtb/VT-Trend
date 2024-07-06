A:: ; Press A to start displaying mouse coordinates
MouseGetPos, xpos, ypos
ToolTip, Mouse coordinates:`nX: %xpos%`nY: %ypos%
return

^Esc::ExitApp ; Press Ctrl + Esc to exit the script
