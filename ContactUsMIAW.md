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
		} catch (err) {
			console.error('Error loading Embedded Messaging: ', err);
		}
	};
</script>
<script type='text/javascript' src='https://spabbaraju-231030-844-demo.my.site.com/ESWContactUsMIAWdeploy1699278255115/assets/js/bootstrap.min.js'></script>

<button id="launchChatButton" onclick="launchChat()">
        Chat will load automatically
    </button>

    <script>
        window.onload=function() {      
        
            console.log( 'Inside onload' );
            let startMessaging = sessionStorage.getItem(
                'messagingStartCheck'
            );
	      console.log( 'startMessaging value is' + startMessaging);

            if ( 
                startMessaging &&
                startMessaging === 'YES'
            ) {

                console.log( 'Messaging was in progress' );        
				/*
					For session continuity when the page loads, 
					Messaging is initiated and launched.
				*/
                initEmbeddedMessaging();
		setTimeout(() => {
			    console.log('Function called after 2000 milliseconds');
                           embeddedservice_bootstrap.utilAPI.launchChat();
			}, 2000);
               
                
            }
	    if (!startMessaging){
                          console.log( 'No Messaging session in progress' );  
            sessionStorage.setItem(
                'messagingStartCheck',
                'YES'
            );
            initEmbeddedMessaging();
            console.log("Loading Messaging now");
            setTimeout(() => {
                embeddedservice_bootstrap.utilAPI
                    .launchChat()
                    .then(() => {
                        console.log("Inside Launch Chat");
                    })
                    .catch(() => {
                        console.log("Inside Launch Chat catch Block");
                    })
                    .finally(() => {
                        console.log("Inside Launch Chat finally Block");
                    });
            }, 5000);
			  
	    }
            
        };

    </script>

</html>
