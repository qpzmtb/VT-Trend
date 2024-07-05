toggle := false
TargetProgramTitle := "ahk_class Ragnarok" ; Specify the program's window title or class here"

F12::
IfWinActive, %TargetProgramTitle%
{
    toggle := !toggle
    if (toggle)
        SetTimer, ColorSearch, 100
    else
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
        Sleep 100
        Loop, 10 ; Repeat the following actions 10 times
        {
            Send {F7}
            Sleep 100
            MouseClick, left, %newX%, %newY%
            Sleep 100
        }
		Sleep 100
        Send {F6}
        Sleep 100
        Send {F8}
    }
    else
    {
        Sleep 100
        Send {F8}
    }
}
return

+::Reload
-::ExitApp
