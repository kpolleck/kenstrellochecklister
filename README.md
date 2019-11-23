# kenstrellochecklister
Javascript code to retrieve checklists from cards on a Trello board.

Welcome to Ken Polleck's Trello Checklister.

I could create this as a simple app you can authorize to your own Trello boards, but for now, I'll leave it that you have to set it up
as your own app.  It took me several hours to work through the issues, but it really should take only 15 minutes to set up if you don't
encounter problems.

Note:  Trello allows "batch" procesing by Trello APis to reduce the rate of API calls (which is limited, but I haven't encountered that problem).
This code does NOT currently use batch requests.

I should enhance this documentation to be more complete, but for now, it is what it is.

If you are using this Trello Checklister, be sure to:

1. Get your App Key https://trello.com/app-key .
2. While on that page, add as an "Allowed Origin" the domain where you plan to deploy the single HTML file.  Ignore the comments about
   redirects.  We won't be using them here.
3. Get your Board ID by finding the URL of your Trello board that looks like https://trello.com/b/<eight-cryptic-characters>/myboardname
   Then, replace the URL after the eight-cryptic-characters with /reports.json like this:
        https://trello.com/b/<eight-cryptic-characters>/reports.json
   From there, your Board ID will be in the very beginning of the JSON.
4. Two Notes:
   a) Currently this code works for only one board, but there is javascript code included that retrieves boards, so you could modify it
   a bit to get checklists from all boards you have access to.  But if you are a Trello user of any significant amount, you probably have
   too many boards to want that anyway.
   b) As you can see, that reports.json file containts pretty much everything on your board.  As an alternative to this code,
   you could just use that result and process it with other tools to retrieve the information you are looking for.
5. Change anywhere there is "xxx" in TrelloChecklisterExample.html.  As of November, 2019, there are only three lines to change:
	<script src="https://api.trello.com/1/client.js?key=xxx"> (Replace with your App Key gathered in setp 1.)
	var myBoardID = 'xxx'; (Replace with your board id.)
	var onlyOnList = "xxx"; (Replace with the name of the list you want to retrieve checklists from.  If you want all checklists from
	        all cards on all lists, search the code and take out the test for list.name == onlyOnList.)
6. Deploy that code onto your webserver.
7. Try it out from your browser!
8. If things aren't working, check that the application has access to your Trello account by checking https://trello.com/<YOUR_NAME>/account.

Best wishes..and enjoy!
- Ken Polleck
