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
{
    ; Color ID: 0x00FF0F
    PixelSearch, Px, Py, 19, 13, 1342, 754, 0x00FF0F, 20, Fast

    if (ErrorLevel = 0)
    {
        newX := Px + 50
        newY := Py + 50
		
        Loop, 10 ; Repeat the following actions 10 times
        {
			ControlSend, ahk_parent, {F7}, ahk_class Ragnarok
			Sleep, 10
			MouseMove, %NewX%, %NewY%
			Sleep, 10
			MouseClick, left, %newX%, %newY%
   			Sleep, 10
        }
		
		Sleep, 100
        ControlSend, ahk_parent, {F6}, ahk_class Ragnarok
        Sleep, 100
        ControlSend, ahk_parent, {F8}, ahk_class Ragnarok
    }
	
    else
    {
        Sleep 100
    }
	
}
return

+::Reload
-::ExitApp
