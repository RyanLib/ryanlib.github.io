<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <script
      type="text/javascript"
      src="https://demo.microstrategy.com/MicroStrategyLibrary/javascript/embeddinglib.js"
    ></script>
  </head>

  <body>
    <div id="embedding-dossier-container" />
    <script>
      let url =
        "https://demo.microstrategy.com/MicroStrategyLibrary/app/B7CA92F04B9FAE8D941C3E9B7E0CD754/27D332AC6D43352E0928B9A1FCAF4AB0"; // https://{env-url}/{libraryName}/app/{projectId}/{dossierId}
      let dossier; // Variable to store the dossier created. Used by Event Handler do not remove!
      let config; // Variable to store the configuration settings for dossier.
      async function runCode() {
        // For more details on configuration properties, see https://microstrategy.github.io/embedding-sdk-docs/add-functionality/methods-and-properties
        config = {
          url: url,
          placeholder: document.getElementById("embedding-dossier-container"),
          containerHeight: "600px",
          containerWidth: "800px",
          customAuthenticationType:
            microstrategy.dossier.CustomAuthenticationType.AUTH_TOKEN,
          customUi: {},
          disableNotification: true,
          dockedComment: {
            dockedPosition: "left",
            canClose: true,
            dockChangeable: false,
            isDocked: false,
          },
          dockedFilter: {
            dockedPosition: "left",
            canClose: true,
            dockChangeable: false,
            isDocked: false,
          },
          dockedTOC: {
            dockedPosition: "left",
            theme: "light",
            canClose: true,
            dockChangeable: false,
            isDocked: false,
          },
          dossierFeature: {
            readonly: false,
          },
          enableCollaboration: true,
          enableCustomAuthentication: false,
          enableResponsive: true,
          filterFeature: {
            enabled: true,
            edit: true,
            summary: true,
          },
          filters: [],
          getLoginToken: function login() {
            console.log("Implement log in to return promise of auth token");
          },
          navigationBar: {
            enabled: true,
            gotoLibrary: true,
            title: true,
            toc: true,
            reset: true,
            reprompt: true,
            share: true,
            comment: true,
            notification: true,
            filter: true,
            options: true,
            search: true,
            bookmark: true,
            edit: false,
          },
          optionsFeature: {
            enabled: true,
            help: false,
            logout: true,
            manage: false,
            showTutorials: false,
          },
          shareFeature: {
            enabled: true,
            invite: false,
            link: true,
            email: false,
            export: true,
            download: false,
            shareDossier: false,
            subscribe: false,
          },
          smartBanner: false,
          tocFeature: {
            enabled: true,
          },
          uiMessage: {
            enabled: true,
            addToLibrary: false,
          },
          visibleTutorials: {
            library: true,
            welcome: false,
            dossier: true,
            notification: false,
          },
          visualizationAppearances: [],
        };
        // INSERT PROPERTIES BELOW HERE

        // INSERT PROPERTIES ABOVE HERE

        // Embed the dossier with the configuration settings
        try {
          dossier = await window.microstrategy.dossier.create(config);
        } catch (error) {
          console.error(error);
        }

        // INSERT METHODS BELOW HERE

        // INSERT METHODS ABOVE HERE
      }
      runCode();
    </script>
  </body>
</html>
