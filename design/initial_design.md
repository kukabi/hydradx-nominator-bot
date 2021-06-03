Idea:
Not very much validator can do in HydraDX now. Tokens are not transferable for now.
Nominators are monitoring their stakes every hour and polkadot.js.org portal is not fast and comfortable enough.
So, I suggest to create a bot with information interesting for Nominators.
I marked optional functionality with {}

enter your HDX address (get it and save)

{/language - very questionable if we need it, maybe the bot is not complicated, do we need to translate it?}

/about information about bot, devs, list of good validators

/help list of commands

/add add an address to follow

/remove remove an address 

/nominatorinfo -> choose your nominator from the list - >

     nominator info:
     
     - address
     
     - stake / nominated stake (here could be a link to active nominations)
     
     - rewards (past rewards sum and unpaid rewards)
     
     {- rewards charts are not necessary now} 

/validators -> choose your nominator ->
	
	you validators list (here is a UI issue: list could be big)
	
	- list:
	
	| name or short addr of valdtr | active/not active | nominated stake | pending rewards
	
	| .............................| active/not active | nominated stake | pending rewards
	
	pending rewards could contain a link to the payout page

{/news -> It could be the great opportunity for a bot to be more useful. For the start I could enter news manually}

{/tutorials “how to”: claim tokens, nominate,validate, request a tip and so on}

/feedback Enter your feedback here. What functionality would you like to see in this bot?
