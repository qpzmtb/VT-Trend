toggle := false
TargetProgramTitle := "ahk_class Ragnarok" ; Specify the program's window title or class here

F12::
IfWinActive, %TargetProgramTitle%

toggle := !toggle
if (toggle) {
    SetTimer, ColorSearch, 100
} else {
    SetTimer, ColorSearch, Off
}
return

ColorSearch:

if (searching)
    return
searching:=1

    PixelSearch, Px, Py, 19, 13, 1342, 754, 0x00FF0F, 20, Fast

    if (ErrorLevel = 0)
    {
        newX := Px + 50
        newY := Py + 50
		
        Loop, 10 ; Repeat the following actions 10 times
        {
			ControlSend, ahk_parent, {F7}, ahk_class Ragnarok
			Sleep, 24 ; setting this too low could break thing but you can try
            		MouseClick, left, %newX%, %newY%, 1, 0 ; not tested , should be fastest.
            ; you could use your way if something happen...
			Sleep, 24 ; same
        }
        
		Sleep, 100    ; needed that long ?
        ControlSend, ahk_parent, {F6}, ahk_class Ragnarok
        Sleep, 100    ; same
        ControlSend, ahk_parent, {F8}, ahk_class Ragnarok
    }
	
    else        ; I don't think this else block is needed anymore (if the logic is correct)
    {
        Sleep 100
    }

searching:=0

return
