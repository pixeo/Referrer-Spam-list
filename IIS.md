#IIS settings
Here's how you can block referrer spam on global server level on IIS

##Requirements
URL rewrite 2.0

##applicationHost.config
Add following snippet inside your `<system.webServer>`
```xml
<rewrite>
	<globalRules>
		<rule name="Block Referrer spam" stopProcessing="true">
			<match url=".*"/>
			<conditions logicalGrouping="MatchAny">
				<add input="{HTTP_REFERER}" pattern="(54\.186\.60\.77)|(76brighton\.co\.uk)|(7makemoneyonline\.com)|(adcash\.com)|(adviceforum\.info)|(alienpayday)|(artobox)|(axisalternativementalhealth)|(baixar\-musicas\-gratis\.com)|(best\-seo\-solution\.com)|(bestwebsitesawards\.com)|(blackhatworth\.com)|(buttons\-for\-website\.com)|(buy\-forum\.ru)|(cenoval\.ru)|(cityadspix\.com)|(darodar\.com)|(descargar\-musica\-gratis\.net)|(econom\.co)|(edakgfvwql\.ru)|(fbdownloader\.com)|(forum\.smailik\.org)|(forum20\.smailik\.org)|(gobongo\.info)|(hulfingtonpost\.com)"/>
				<add input="{HTTP_REFERER}" pattern="(humanorightswatch\.org)|(ilovevitaly\.co)|(ilovevitaly\.com)|(ilovevitaly\.ru)|(iskalko\.ru)|(kambasoft\.com)|(lomb\.co)|(lomb\.co)|(lombia\.co)|(lumb\.co)|(luxup\.ru)|(medispainstitute)|(myftpupload\.com)|(o\-o\-6\-o\-o\.com)|(o\-o\-6\-o\-o\.ru)|(o\-o\-8\-o\-o\.ru)|(paparazzistudios\.com\.au)|(powitania\.pl)|(priceg\.com)|(prlog\.ru)|(ranksonic\.info)|(s\.click\.aliexpress\.com)|(savetubevideo\.com)|(savetubevideo\.info)|(screentoolkit\.com)|(see\-your\-website\-here\.com)|(semalt\.com)|(semalt\.semalt\.com)"/>
				<add input="{HTTP_REFERER}" pattern="(seoexperimenty\.ru)|(sharebutton\.net)|(simple\-share\-buttons\.com)|(site14\.simple\-share\-buttons\.com)|(site18\.simple\-share\-buttons\.com)|(site22\.simple\-share\-buttons\.com)|(site30\.simple\-share\-buttons\.com)|(slftsdybbg\.ru)|(smailik\.org)|(social\-buttons\.com)|(socialseet\.ru)|(sq01)|(srecorder\.com)|(superiends\.org)|(tasteidea\.com)|(torontoplumbinggroup\.com)|(vodkoved\.ru)|(website\-errors\-scanner\.com)|(websocial\.me)|(ykecwqlixx\.ru)"/>
				<add input="{HTTP_REFERER}" pattern="(chinese\-amezon\.com)|(e\-buyeasy\.comerot\.co)|(floating\-share\-buttons\.com)|(free\-social\-buttons\.com)|(get\-free\-social\-traffic\.com)|(hongfanji\.com)|(free\-floating\-buttons\.com)|(success\-seo\.com)|(videos\-for\-your\-business\.com)|(event\-tracking\.com)|(Get\-Free\-Traffic\-Now\.com)"/>
				<add input="{HTTP_REFERER}" pattern="(traffic2cash\.xyz)|(w3javascript\.com)|(site\-54737596\-1\.snip\.tw)|(visitors\.genie\-connect\.com)|(quit\-smoking\.ga)|(top1\-seo\-service\.com)|(top1\-seo\-service\.com)|(build\-a\-better\-business\.2your\.site)|(topseoservices\.co)|(website\-stealer\.nufaq\.com)|(share\-buttons\.xyz)|(brucrm01\.be\.stibbe\.int)|(santasgift\.ml)|(website\-stealer\-warning\.hdmoviecamera\.net)|(71510028\.forum\.nufaq\.com)|(site\-71510028\-1\.snip\.tw)"/>
				<add input="{HTTP_REFERER}" pattern="(cstc\.be)|(forum\.muratordom\.pl)|(free\-traffic\.xyz)|(net\-profits\.xyz)|(rtsys\.rtrk\.be)|(social\-widget\.xyz)|(web\-revenue\.xyz)|(с\.новым\.годом\.рф)"/>
			</conditions>
			<action type="AbortRequest"/>
		</rule>
	</globalRules>
</rewrite>
```
