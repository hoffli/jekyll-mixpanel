# Jekyll + Mixpanel
## How to get visitor IP address on a static or generated website

### 1/ Copy the mixpanel code they provide you 

```
<!-- start Mixpanel -->hsbjuwbubcbc
djueduweuweuwuef a lot of crap
ushuwuhswshu
<!-- end Mixpanel -->
```

Put that before `</head>` or `{% include it.html %}`

### 2/ Detect the visits

To detect fully loaded websites only put this  in footer section.

```
	<script type="application/javascript">
	  function getIP(json) {
	     console.log(json.ip);
			mixpanel.identify( json.ip );
			mixpanel.people.set({
				"$first_name": json.ip ,
				"$ip": json.ip,
			});
			mixpanel.track("{{page.title}}");
	  }
	</script>
	<script type="application/javascript" src="https://api.ipify.org?format=jsonp&callback=getIP"></script>
```

* It uses ipify.org which provides API for getting a visitor IP address via JavaScript. 
* It identifies repeated IP addresses.
* Mixpanel will also detect other basic information like browser type, referrer etc. 

Good alternative if you don't want to do Google Analytics for some reason.
