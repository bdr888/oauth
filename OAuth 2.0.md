


OAuth 2.0

"This protocol allows third-party applications to grant limited access to an HTTP service, either on behalf of a resource owner or by allowing the third-party application to obtain access on its own behalf. Access is requested by a client, it can be a website or a mobile application for example."
http://www.bubblecode.net/en/2016/01/22/understanding-oauth2/


 Login flow
 
 Client: Open a popup window via $auth.authenticate('provider name').
 Client: Sign in with that provider, if necessary, then authorize the application.
 Client: After successful authorization, the popup is redirected back to your app, e.g. http://localhost:3000, with the code (authorization code) query string parameter.
 Client: The code parameter is sent back to the parent window that opened the popup.
 Client: Parent window closes the popup and sends a POST request to /auth/provider withcode parameter.
 Server: Authorization code is exchanged for access token.
 Server: User information is retrived using the access token from Step 6.
 Server: Look up the user by their unique Provider ID. If user already exists, grab the existing user, otherwise create a new user account.
 Server: In both cases of Step 8, create a JSON Web Token and send it back to the client.
 Client: Parse the token and save it to Local Storage for subsequent use after page reload.
https://github.com/sahat/satellizer#authloginuser-options

Resources:
https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2
https://aaronparecki.com/2012/07/29/2/oauth2-simplified
http://www.bubblecode.net/en/2016/01/22/understanding-oauth2/
https://github.com/sahat/satellizer#authloginuser-options