<html>
	<script type='text/javascript'>
	function initEmbeddedMessaging() {
		console.log('Inside initEmbeddedMessaging');
		try {
			embeddedservice_bootstrap.settings.language = 'en_US'; // For example, enter 'en' or 'en-US'

			embeddedservice_bootstrap.init(
				'00D5g00000KLfIK',
				'Contact_Us_MIAW_deployement',
				'https://spabbaraju-231030-844-demo.my.site.com/ESWContactUsMIAWdeploy1699278255115',
				{
					scrt2URL: 'https://spabbaraju-231030-844-demo.my.salesforce-scrt.com'
				}
			);
                 embeddedservice_bootstrap.utilAPI.launchChat();
		} catch (err) {
			console.error('Error loading Embedded Messaging: ', err);
		}
	};
</script>
<script type='text/javascript' src='https://spabbaraju-231030-844-demo.my.site.com/ESWContactUsMIAWdeploy1699278255115/assets/js/bootstrap.min.js'></script>

<button id="launchChatButton" onclick="launchChat()">
        Chat will load automatically
    </button>

</html>
