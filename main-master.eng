#use <Engi/Unpack/Tool.e> as X

// Calling Conv. scanner, credits to: math.rand0m.
func _Env Scan(a1):
  #X.CheckState(a1, 6) // Goes from that address, up 6 lines. If calling conv. not found, try method: 2.
  if #X.StateExists(_Env.split_by(", ", "__cdecl, __fastcall, __thiscall")) :
    //Alright so we found the calling convention, lets print it!
    #X.OPC(push, #X.State, _Env.ToString()) // Pushes the calling conv to the stack.
    #X.OPC(push, 0) // Took a long time to figure out, but prevents the game from closing down!
    #X.OPC(call, _printf, -1) // You have to do it thru OPCodes, else you are not able to call the stack from Engii!
  close:
    end(true) //Ends the Scan function and doesn't end the whole program/task. Cant work without.
close:
  //Do nothing here buddy, this is a big in the language we hope they fix it!


ConsoleStart(_Env.this, "Offset Logger [Jaden-Developer]") //Creates Console with text.
if GetRunningProcess.ByName("Roblox%s") do: //If RobloxPlayerBeta.exe process is running!
  Down.ByLines(3) //Goes down 3 lines in code, "jmp"
close:
  close(true)
//Jumps here!

#X.OPC(push, 0x4030C0, _Env.ToString()) // lua_getfield, method should be: PATCHED
#X.OPC(push, NULL, NULL) // 2:nd argument is not needed if we are not getting the calling convention. But we have other scans for that!
// + would need updating, its hard.
// String: "global sown as", patched! Pretty old method but coming with an update soon.
#X.OPC(call, _printf, -2) // Prints the offset out in the console, but how about the convention? Let's scan for it!

_Env.Scan(0x4030C0) // Still not updated, don't try to debug it thanks. Will get you detected and probably logged.

//
Should print out:

  0xOFFSET%s
  __convention
\\
