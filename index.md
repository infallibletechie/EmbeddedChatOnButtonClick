<html>
    <input type="button" value="Start Chat" onclick="startChat();"/><br/><br/><br/>
    
  <style type='text/css'>
    .embeddedServiceHelpButton .helpButton .uiButton {
      background-color: #005290;
      font-family: "Arial", sans-serif;
    }
    .embeddedServiceHelpButton .helpButton .uiButton:focus {
      outline: 1px solid #005290;
    }
  </style>

  <script type='text/javascript' src='https://service.force.com/embeddedservice/5.0/esw.min.js'></script>
  <script type='text/javascript'>
    var initESW = function(gslbBaseURL) {
      embedded_svc.settings.displayHelpButton = false;
      embedded_svc.settings.language = ''; //For example, enter 'en' or 'en-US'

      embedded_svc.settings.enabledFeatures = ['LiveAgent'];
      embedded_svc.settings.entryFeature = 'LiveAgent';

      embedded_svc.init(
        'https://infallibletechie9-dev-ed.my.salesforce.com',
        'https://infallibletechie9-dev-ed.my.site.com/',
        gslbBaseURL,
        '00D5f000001yZYJ',
        'Embedded_Chat',
        {
          baseLiveAgentContentURL: 'https://c.la4-c1-ia4.salesforceliveagent.com/content',
          deploymentId: '5725f000000TllG',
          buttonId: '5735f000000Tm6g',
          baseLiveAgentURL: 'https://d.la4-c1-ia4.salesforceliveagent.com/chat',
          eswLiveAgentDevName: 'EmbeddedServiceLiveAgent_Parent04I5f000000PJ1GEAW_17c32b6b665',
          isOfflineSupportEnabled: true
        }
      );
    };

    if (!window.embedded_svc) {
      var s = document.createElement('script');
      s.setAttribute('src', 'https://infallibletechie9-dev-ed.my.salesforce.com/embeddedservice/5.0/esw.min.js');
      s.onload = function() {
        initESW(null);
      };
      document.body.appendChild(s);
    } else {
      initESW('https://service.force.com');
    }
  </script>
  
    <script>
        function startChat() {
            
            console.log( 'Inside Start Chat' );
            embedded_svc.liveAgentAPI.startChat({
                directToAgentRouting: {
                buttonId: "5735f000000Tm6g",
                fallback: true
            },
            extraPrechatInfo: [],
            extraPrechatFormDetails: []
            });
            
        }
        
        function clearSession() {
            
            console.log( 'Inside Close Chat' );
            embedded_svc.liveAgentAPI.clearSession();
            
        }
    </script>
</html>
