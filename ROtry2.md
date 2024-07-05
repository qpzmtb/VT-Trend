toggle := false

#IfWinActive, ("ahk_class Ragnarok")
$F12::
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
        Sleep, 100
        Loop, 10 ; Repeat the following actions 10 times
        {
            ControlSend, ahk_parent, {i}, ahk_class Ragnarok
            Sleep, 100
            MouseClick, left, %newX%, %newY%
            Sleep, 100
        }
		Sleep, 100
        ControlSend, ahk_parent, {o}, ahk_class Ragnarok
        Sleep, 100
        ControlSend, ahk_parent, {p}, ahk_class Ragnarok
    }
    else
    {
        Sleep 100
        ControlSend, ahk_parent, {p}, ahk_class Ragnarok
    }
}
return

+::Reload
-::ExitApp
