# DELTA_UI

PROJECT: DELTA UI

BY: Oo

COMPANY: io

V: 1.1

LIC: FREE if you leave in the credit

$: Any IN-GAME donations are welcome

https://gist.github.com/johnpenny/6b1632204244df89d94de36c3a0bf203

---------------------------------------------------------------------------

#### HOW TO INSTALL

1) You must have ISAN installed. Grab a new BASIC Yolol chip and a Memory chip (8 fields needed), and a spare connected text screen
2) Rename the screen to "."
3) IF NOT AlREADY DONE Modify ISAN to activate 'po', and allow modules; as shown in the ISAN doc: //isan.to/isan.pdf#page=9
   If your ISAN already had external coordinate values for modules, you don't need to add the memory slots for XX YY ZZ.
4) Install the memory chip and write in the field names AND values (without the "") shown in the 'MEMORY CHIP VARS' section below
5) Paste all the DELTA UI Yolol code into your new Yolol chip
6) Reboot the chip by clearing the . screen value - you may have to do it a couple of times to work
7) Re-name your Transponder's safezone bool to 'TSZ' (OR set TSZ in the code to the name of yours)
8) Memory strings 'dus' and 'dud' are the safezone indication texts 'sz' and '!!' which you may want to edit to your liking (reboot!)
9) If you have any issues the first step is to reboot the chip by clearing the screen, as with ISAN

#### USING

- The 'compass' shows your axial movement DELTA, and NOT 'where you are looking'.

- It WAS called compass simply because Starbase has NESW transmitters. Now it's called DELTA UI

- The middle (depth) indicator shows the planet EOS, with arrows pointing IN when you are going towards it, and OUT when you move away
and go towards the asteroid belt (ONLY if you are out from the Origin ring).

-These visual frames of reference are NOT set in stone, as once you move far enough away from the origin ring, you must also consult
the ISAN coords screen to ensure you are in the right area of space. Then you can glance at the DELTA UI to check your delta.

- If lost and you wish to return to the origin ring, you should aim for coords 0,0,0 and the ring should come into view.

- ISAN: https://isan.to/isan.pdf

- With all that said, this is more of a glancing indicator, and a cool panel, than a nav tool.

---------------------------------------------------------------------------

#### MEMORY CHIP VARS (5 for this, 3 for ISAN, 2 spare)

duh = "——————————\n"
dup = "«◦»"
dun = "»◦«"
dus = "   「 sz 」\n"
dud = "   「 !! 」\n"
xx = (DYNAMIC FROM ISAN)
yy = (DYNAMIC FROM ISAN)
zz = (DYNAMIC FROM ISAN)

---------------------------------------------------------------------------

#### SCREEN NAME

. (a single full stop)

---------------------------------------------------------------------------

#### TRANSPONDER

Your transponder safe zone bool should be named as :TSZ, or edit the yolol to match yours

---------------------------------------------------------------------------

#### ISAN - ALLOW MODULES

1) Allow modules by making coords external (memory chip) by following instructions here: //isan.to/isan.pdf#page=9
2) I recommend you turn on po by changing po=1 to po=0 on the top line of ISAN, if it is not already done

---------------------------------------------------------------------------

#### OPTIONALLY CHANGE THE TITLE

On line 4 the title string can be changed but you must keep it below 8 chars long and do not remove the \n
sl=" NAV  :.\n"
sl=" DIR  :.\n"
sl="Hello...\n"
sl="      :.\n"

---------------------------------------------------------------------------

#### REBOOTING

To reboot and init new variables, just delete the content of your text screen field, you may have to try a few times.
Last resort: put a space between the 1 and 4 on the last GOTO14 on line 20, then immediately delete the space.

#### NOTHING WORKS! HELP!

Sometimes I get memory fields or chips that will not load or update.
I am currently not aware how to solve this, seems like a game bug.
I just delete everything and re-paste it all.

If you need to start over I highly recommend downloading Visual Studio Code, and grabbing this extension to allow you to paste Yolol 
into game quickly: //marketplace.visualstudio.com/items?itemName=dbaumgarten.vscode-yolol

You can see the instructions for quick pasting here: //dbaumgarten.github.io/yodk/#/vscode-instructions?id=auto-typing-into-starbase
