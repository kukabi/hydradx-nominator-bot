## Initial Ideas

There's not very much a validator can do in HydraDX now. Tokens are not transferable for now.

Nominators are monitoring their stakes every hour through [polkadot.js](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Frpc-01.snakenet.hydradx.io#), which is not fast nor very user-friendly.

So, I suggest to create a bot with information interesting for Nominators.
I marked optional functionality with {}.

On chat startup: `enter your HDX address (get it and save)`

{`/language` - very questionable if we need it, maybe the bot is not complicated, do we need to translate it?}

> **@kukabi:** I agree this is not a critical feature now. But it'd be good to be prepared for future i18n.

> **@osoiotoko:**✅

`/about` information about bot, devs, list of good validators

> **@kukabi:** I think we can separate the bot's `/about` from the network info. How about a `/network` command to get that sort of info? Or just have a `/validators` command to display select validators, and rename the same-named command below as I suggested in the comments for it?

> **@osoiotoko:** "list of good validators" - is some advertizing here. Didn't mean to make big things here. 

`/help` list of commands

> **@kukabi:** ✅

`/add` add an address to follow

> **@kukabi:** ✅

`/remove` remove an address 

> **@kukabi:** ✅

`/nominatorinfo` -> choose your nominator from the list - >

    nominator info:
     
    - address
     
    - stake / nominated stake (here could be a link to active nominations)

    - rewards (past rewards sum and unpaid rewards)
    
    {- rewards charts are not necessary now} 
    
> **@kukabi:** ✅

`/validators` -> choose your nominator ->
	
    nominated validator list (here is a UI issue: list could be big)
    
    - list:
    
    | name or short addr of valdtr | active/not active | nominated stake | pending rewards
	
	| .............................| active/not active | nominated stake | pending rewards
	
	pending rewards could contain a link to the payout page

> **@kukabi:** I think `/nominations` might be a better name for this command.
> 
> Aggregate/summary info like `x validators, x active, x total pending` may be helpful here too, at the top or the bottom of the result. Not sure but maybe statistical data like `(total nominated stake of all nominated validators) / (total stake on the network)` may help too?
>
> I agree with you regarding the potential UI issue. I think Telegram supports tabular data through markdown - we should take a look at that and experiment with different formats. Pagination is also another pattern - but not sure how practical it can be on Telegram.

> **@osoiotoko:** great point: `/nominations` is much more clear: here we suggest an information about current nominations. 
> And more - Summary (and notifications) is the MOST imoptant feature, because user wants to see the picture fast to be sure that everything is ok.
> So we can start summary with `x validators, x active, x total pending` 
> may be with additional stake info for more clear info:
> `Total: n HDX nominated to x validators` 
> `Active: n HDX nominated  to x active validators`
> `Pending: x your validators are in next set`

{`/news` -> It could be the great opportunity for a bot to be more useful. For the start I could enter news manually}

> **@kukabi:** I agree. Very cool idea.

{`/tutorials` “how to”: claim tokens, nominate,validate, request a tip and so on}

> **@kukabi:** Good value.

`/feedback` Enter your feedback here. What functionality would you like to see in this bot?

> **@kukabi:** ✅

### Notifications

> **@kukabi:** Just adding some notifications off the top of my head, let's elaborate.

- One of the nominated validators receives/loses a nomination. > **@osoiotoko:** I am not sure this info is valuable
- A nominated validator gets in the active set. 
- A payout is made to one of the nominator accounts.
- Pending payouts for any nominators at the end of every era. > **@osoiotoko:** any nominators = this user nominators ?
- A validator gets offline (doesn't send the `imonline` message).
- A validator gets slashed.
- ...

> **@osoiotoko:** - ... big news

> notifications is the coolest thing in this bot. Are we going to allow custom on/off? Seems like next version?

### Validator Ranking

> **@kukabi:** I don't know about the existing models of validator ranking, but I saw a few community contributions around this. Would help the `/validators` command to specify the ranking algorithm.

> **@osoiotoko:** Yes, Good point, lets rename previous `/validators` to `/nominations` 
> and make a very useful feature - info about validators here in `/validators`.
> Here I need to comment:
> When user is changing his validators list, he wants to know: 
> 1. what validators will be in next set (some users jump from val to val according to this)
> 2. what are the chances for this validator to get active (total validator stake / lowest stake in active set
> 3. will his stake get rewards (if validator is oversubbed, nominator stake must be in first 64nom_stake(by amount) to get rewards.
> 4. some recommendations (if these recommendations are from the clear algorythm - it would be great, there is some implementation in polkadot.js)
> 5. may be some summary info about validators (ID/name , %, total stake)
