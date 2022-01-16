# Hakai Dec 16 2022

## UPDATE

	January 16 2022

## CHANGES

Corrected some mounting issues in load process
Ported the Force FX chain assets to MPC assets which are interoperable in both Force and MPC programs.
Also created and added a number of FX Chains.
Attempted to correct the bug in my midi interface library that prevents MPC Live II users from using Hakai


## *NEW* STOCK-SYNTHS WHAT AND WHY

Here is how to make the artwork show up on your MPC again:

WHY: In order to make room to fit all the force content into the rom, I had to prune some content so the content I choose to remove was the artwork for all the plugins as well as the TestApp binaries for initializing. (generally not used)

HOW: Copy them to your internal Synths directory or, place them on usb or SD card. It is safe to "transpose" the folders with the content Akai released. (hype, molotron, odyssey etc)

*Hackers beware* DO NOT attempt to copy them to the root file system they wont fit, its 135 mb of data... you'll just fill your rootfs up


## SPOOFING VIA CARD NAMING

To spoof your unit into a certain mode name your sd or usb card one of these:
  
	X, ONE, LIVE, LIVE2, FORCE6, FORCE
  

## ABOUT MIDI.CFG

After the first time you've booted with a specially named card it will then copy the midi.cfg to the memstick. You can then edit the mapping with your own, this is a tedious process.

A midi controller is not needed for force, it works with the regular mpc matrix, however if you have an APC, Launchpad, Smartpad or Push you can very likely map it in the midi config

When editing the midi config do not add lines, do not delete lines. ONLY MODIFY THE VALUES.

Items in the midi config denoted with the CONTROLLER_ prefix are things you'll map your matrix values to. (these are for your matrix pads)

Items in the midi config denoted with the FORCE_ prefix are things you'll map your internal interface buttons to.. (if you know how otherwise leave them alone)


## HAKAI SPECIAL FEATURES

There are some special feature's I've coded in. Since the play start button was free and MPC ONE, LIVE and LIVE 2 units are limited on buttons I programmed a special *shift-like* feature.

When "hakai shift" (play start) is held down you can use the select and launch features from the matrix pad of the main MPC unit. (when not held they do regular force matrix things)

When "hakai shift" (play start) is held down you can use the qlink buttons to choose record arm, solo, mute, and clip stop

Here is an over all feature i added for all MPC units, since the mpc only has an 4x4 matrix grid- i coded it so if you double tap the qlink bank buttons it will switch the matrix quadrant.

Bank A is top left

Bank B is top right

Bank C is bottom left

Bank D is bottom right


## THINGS TO KNOW

Currently, the lights on midi controllers do not work, that's a but of a monumental undertaking because some of them use note values, others use continuous control, and some use sysex.

If you're experienceing a feed back loop in your matrix pad make sure you go to the mpc settings > midi and disable "track" and "master" for the matrix pad.
You dont want it linked to either of those options.


## MORE

Here is a list of midi values for the MPC's internal interface incase anyone doesnt like the default mapping they can use these for reference.

	MPC_KNOB 					= 0x64, //this is a cc not a note
	
	MPC_QLINK_1 				= 0x10,
	MPC_QLINK_2 				= 0x11,
	MPC_QLINK_3 				= 0x12,
	MPC_QLINK_4 				= 0x13,
	MPC_QLINK_5 				= 0x14,
	MPC_QLINK_6 				= 0x15,
	MPC_QLINK_7 				= 0x16,
	MPC_QLINK_8 				= 0x17,
	MPC_QLINK_9  				= 0x18,
	MPC_QLINK_10 				= 0x19,
	MPC_QLINK_11 				= 0x1A,
	MPC_QLINK_12 				= 0x1B,
	MPC_QLINK_13 				= 0x1C,
	MPC_QLINK_14 				= 0x1D,
	MPC_QLINK_15 				= 0x1E,
	MPC_QLINK_16 				= 0x1F,
	
	MPC_PAD_01 					= 0x25,
	MPC_PAD_02 					= 0x24, 
	MPC_PAD_03 					= 0x2A, 
	MPC_PAD_04 					= 0x52,
	MPC_PAD_05 					= 0x28, 
	MPC_PAD_06 					= 0x26, 
	MPC_PAD_07 					= 0x2E, 
	MPC_PAD_08 					= 0x2C,
	MPC_PAD_09 					= 0x30, 
	MPC_PAD_10 					= 0x2F, 
	MPC_PAD_11 					= 0x2D, 
	MPC_PAD_12 					= 0x2B,
	MPC_PAD_13 					= 0x31, 
	MPC_PAD_14 					= 0x37, 
	MPC_PAD_15 					= 0x33, 
	MPC_PAD_16 					= 0x35,
	
	MPC_Q_LINK_SELECT 			= 0x00,
	//UNKNOWN					= 0x01,
	MPC_PROG_EDIT 				= 0x02,
	//UNKNOWN					= 0x03,
	//UNKNOWN					= 0x04,
	//UNKNOWN					= 0x05,
	MPC_SAMPLE_EDIT 			= 0x06,
	//UNKNOWN					= 0x07
	MPC_ERASE 					= 0x09,
	//UNKNOWN					= 0x0A,
	MPC_NOTE_REPEAT 			= 0x0B,
	MPC_TC 						= 0x0C,
	//UNKNOWN					= 0x0D,
	//UNKNOWN					= 0x0E,
	//UNKNOWN					= 0x0F,
	//UNKNOWN					= 0x10,
	//UNKNOWN					= 0x11,
	//UNKNOWN					= 0x12,
	//UNKNOWN					= 0x13,
	//UNKNOWN					= 0x14,
	//UNKNOWN					= 0x15,
	//UNKNOWN					= 0x16,
	//UNKNOWN					= 0x17,
	//UNKNOWN					= 0x18,
	//UNKNOWN					= 0x19,
	//UNKNOWN					= 0x1A,
	//UNKNOWN					= 0x1B,
	//UNKNOWN					= 0x1C,
	//UNKNOWN					= 0x1D,
	//UNKNOWN					= 0x1E,
	//UNKNOWN					= 0x1F,
	//UNKNOWN					= 0x20,
	//UNKNOWN					= 0x21,
	//UNKNOWN					= 0x22,
	MPC_BANK_A 					= 0x23,
	MPC_BANK_B 					= 0x24,
	MPC_BANK_C 					= 0x25,
	MPC_BANK_D 					= 0x26,
	MPC_FULL_LEVEL 				= 0x27,
	MPC_SIXTEEN_LEVELS 			= 0x28,
	MPC_STEP_SEQ 				= 0x29,
	MPC_NEXT_SEQ 				= 0x2A,
	MPC_TRACK_MUTE 				= 0x2B,
	//UNKNOWN					= 0x2C,
	//UNKNOWN					= 0x2D,
	//UNKNOWN					= 0x2E,
	//UNKNOWN					= 0x2F,
	//UNKNOWN					= 0x30,
	MPC_SHIFT 					= 0x31,
	MPC_BROWSE 					= 0x32,
	MPC_MAIN 					= 0x34,
	MPC_TEMPO 					= 0x35,
	MPC_PLUS 					= 0x36,
	MPC_MINUS 					= 0x37,
	MPC_UP		 				= 0x38,
	MPC_DOWN			 		= 0x39,
	MPC_SELECT					= 0x3A,
	MPC_PROJECT		 			= 0x3B, //x these control qlink options
	MPC_PROGRAM		 			= 0x3C, //x these control qlink options
	MPC_PAD_SCENE				= 0x3D, //x these control qlink options
	MPC_PAD_PARAM	 			= 0x3E, //x these control qlink options
	MPC_SCREEN_CONTROL	 		= 0x3F, //x these control qlink options
	//UNKNOWN					= 0x40,
	MPC_LEFT			 		= 0x41, //x
	MPC_RIGHT			 		= 0x42, //x
	MPC_UNDO 					= 0x43,
	MPC_EVENT_BACK			 	= 0x44, //x
	MPC_EVENT_FORWARD			= 0x45, //x
	MPC_LOCATE		 			= 0x46, //x
	MPC_START			 		= 0x47, //x
	MPC_END						= 0x48, //x
	MPC_REC 					= 0x49,
	MPC_REC_ARM		 			= 0x4A, //x
	MPC_READ_WRITE		    	= 0x4B, //x
	MPC_MUTE		 			= 0x4C, //x
	MPC_SOLO		 			= 0x4D, //x
	MPC_F_KEY		 			= 0x4E, //x
	//UNKNOWN					= 0x4F,
	MPC_OVERDUB 				= 0x50,
	MPC_STOP 					= 0x51,
	MPC_PLAY 					= 0x52,
	MPC_PLAY_START 				= 0x53,
	MPC_QLINK_1_TOUCH 			= 0x54,
	MPC_QLINK_2_TOUCH 			= 0x55,
	MPC_QLINK_3_TOUCH 			= 0x56,
	MPC_QLINK_4_TOUCH 			= 0x57,
	MPC_QLINK_5_TOUCH 			= 0x58,
	MPC_QLINK_6_TOUCH 			= 0x59,
	MPC_QLINK_7_TOUCH 			= 0x5A,
	MPC_QLINK_8_TOUCH 			= 0x5B,
	MPC_QLINK_9_TOUCH 			= 0x5C,
	MPC_QLINK_10_TOUCH 			= 0x5D,
	MPC_QLINK_11_TOUCH 			= 0x5E,
	MPC_QLINK_12_TOUCH 			= 0x5F,
	MPC_QLINK_13_TOUCH 			= 0x60,
	MPC_QLINK_14_TOUCH 			= 0x61,
	MPC_QLINK_15_TOUCH 			= 0x62,
	MPC_QLINK_16_TOUCH 			= 0x63,
	MPC_1			 			= 0x64,
	MPC_2			 			= 0x65,
	MPC_3			 			= 0x66,
	MPC_4			 			= 0x67,
	MPC_5			 			= 0x68,
	MPC_6			 			= 0x69,
	MPC_7			 			= 0x6A,
	MPC_8			 			= 0x6B,
	MPC_9			 			= 0x6C,
	MPC_0			 			= 0x6D,
	MPC_MINUS_PLUS				= 0x6E,
	MPC_ENTER		 			= 0x6F,
	MPC_KNOB_PUSH 				= 0x6F,
	//UNKNOWN					= 0x70,
	//UNKNOWN					= 0x71,
	//UNKNOWN					= 0x72,
	MPC_PAD_MIXER	 			= 0x73, //x
	MPC_TRACK_MIX 				= 0x74,
	//UNKNOWN					= 0x75,
	//UNKNOWN					= 0x76,
	//UNKNOWN					= 0x77,
	//UNKNOWN					= 0x78,
	//UNKNOWN					= 0x79,
	MPC_COPY 					= 0x7A,
	MPC_MENU 					= 0x7B,
	//UNKNOWN					= 0x7C,
	MPC_SAMPLER 				= 0x7D,
	MPC_XYFX					= 0x7E, //x
	MPC_PAD_PERFORM	 			= 0x7F, //x


## DEFAULT BUTTON LAYOUT FOR MPC INTERFACE (FOR REFERENCE)
CONFIG_ items are the force functions available for mapping MPC_ items are what they are currently tied to. 
Dont try to use these tags in your configuration file they will not work, this is just here for a reference on what is linked to what by default

	//FORCE FNC				  //MPC BUTTON
	CONFIG_NAVIGATE			= MPC_NEXT_SEQ
	CONFIG_KNOBS			= MPC_Q_LINK_SELECT
	CONFIG_MENU				= MPC_MENU
	CONFIG_MATRIX			= MPC_MAIN
	CONFIG_NOTE				= MPC_SIXTEEN_LEVELS
	CONFIG_CLIP				= MPC_SAMPLE_EDIT
	CONFIG_MIXER			= MPC_TRACK_MIX
	CONFIG_LOAD				= MPC_BROWSE
	CONFIG_SAVE				= MPC_TRACK_MUTE
	CONFIG_EDIT				= MPC_SAMPLE_EDIT
	CONFIG_DELETE			= MPC_ERASE
	CONFIG_PROG_EDIT		= MPC_PROG_EDIT
	CONFIG_SHIFT			= MPC_SHIFT
	CONFIG_TRACK_EDIT		= MPC_SAMPLER
	CONFIG_SELECT			= MPC_SELECT
	CONFIG_TEMPO			= MPC_TEMPO
	CONFIG_PLUS				= MPC_PLUS
	CONFIG_MINUS			= MPC_MINUS
	CONFIG_LAUNCH_1			= MPC_1
	CONFIG_LAUNCH_2			= MPC_2
	CONFIG_LAUNCH_3			= MPC_3
	CONFIG_LAUNCH_4			= MPC_4
	CONFIG_LAUNCH_5			= MPC_5
	CONFIG_LAUNCH_6			= MPC_6
	CONFIG_LAUNCH_7			= MPC_7
	CONFIG_LAUNCH_8			= MPC_8
	CONFIG_UNDO				= MPC_UNDO
	CONFIG_LOCATE			= MPC_LOCATE
	CONFIG_REC				= MPC_REC
	CONFIG_STOP				= MPC_STOP
	CONFIG_PLAY				= MPC_PLAY
	CONFIG_MUTE				= MPC_MUTE
	CONFIG_SOLO				= MPC_SOLO
	CONFIG_REC_ARM			= MPC_REC_ARM
	CONFIG_CLIP_STOP		= MPC_READ_WRITE
	CONFIG_STOP_ALL			= MPC_OVERDUB
	CONFIG_QUANTIZE			= MPC_TC
	CONFIG_ENCODER_PRESS	= MPC_ENCODER_PRESS
	CONFIG_UP				= MPC_UP
	CONFIG_DOWN				= MPC_DOWN
	CONFIG_LEFT				= MPC_LEFT
	CONFIG_RIGHT			= MPC_RIGHT
	CONFIG_LAUNCH			= MPC_FULL_LEVEL
	CONFIG_STEP_SEQ			= MPC_STEP_SEQ
	CONFIG_ARP				= MPC_NOTE_REPEAT
	CONFIG_COPY				= MPC_COPY
