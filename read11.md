# **OAuth**
# 1. what is OAuth?
OAuth allows websites and services to share assets among users. It is widely accepted, but be aware of its vulnerabilities.

# 2. Give an example of what using OAuth would look like.
OAuth allows websites and services to share assets among users. It is widely accepted, but be aware of its vulnerabilities.
# 3. How does OAuth work?  are the steps that it takes to authenticate the user?
<ol>
<li>The first website connects to the second website on behalf of the user, using OAuth, providing the user’s verified identity.</li>
<li>The second site generates a one-time token and a one-time secret unique to the transaction and parties involved.</li>
<li>The first site gives this token and secret to the initiating user’s client software.</li>
<li>The client’s software presents the request token and secret to their authorization provider (which may or may not be the second site).</li>
<li>If not already authenticated to the authorization provider, the client may be asked to authenticate. After authentication, the client is asked to approve the authorization transaction to the second website.</li>
<li>The user approves (or their software silently approves) a particular transaction type at the first website.</li>
<li>The user is given an approved access token (notice it’s no longer a request token).</li>
<li>The user gives the approved access token to the first website.</li>
<li>The first website gives the access token to the second website as proof of authentication on behalf of the user.</li>
<li>The second website lets the first website access their site on behalf of the user.</li>
<li>The user sees a successfully completed transaction occurring.</li>
<li>OAuth is not the first authentication/authorization system to work this way on behalf of the end-user. In fact, many authentication systems, notably Kerberos, work similarly. What is special about OAuth is its ability to work across the web and its wide adoption. It succeeded with adoption rates where previous attempts failed (for various reasons).</li>
</ol>
# what is OpenID?


# **Authorization and Authentication flows**

# 1. what is the difference between authorization and authentication?
authorization:give accsess
authentication:say who is who

# 2. what is Authorization Code Flow?
Because regular web apps are server-side apps where the source code is not publicly exposed, they can use the Authorization Code Flow (defined in OAuth 2.0 RFC 6749, section 4.1), which exchanges an Authorization Code for a token. Your app must be server-side because during this exchange, you must also pass along your application's Client Secret, which must always be kept secure, and you will have to store it in your client.
# 3. what is Authorization Code Flow with Proof Key for Code Exchange (PKCE)?
<ol><li><p>The user clicks <b>Login</b> within the regular web application.</p></li><li><p>Auth0's SDK redirects the user to the Auth0 Authorization Server (<a href="https://auth0.com/docs/api/authentication#authorization-code-grant"><code>/authorize</code> endpoint</a>).</p></li><li><p>Your Auth0 Authorization Server redirects the user to the login and authorization prompt.</p></li><li><p>The user authenticates using one of the configured login options and may see a consent page listing the permissions Auth0 will give to the regular web application.</p></li><li><p>Your Auth0 Authorization Server redirects the user back to the application with an authorization&nbsp;<code>code</code>, which is good for one use.</p></li><li><p>Auth0's SDK sends this&nbsp;<code>code</code> to the Auth0 Authorization Server (<a href="https://auth0.com/docs/api/authentication?http#authorization-code-flow43"><code><b>/oauth/token</b></code> endpoint</a>) along with the application's Client ID and Client Secret.</p></li><li><p>Your Auth0 Authorization Server verifies the code, Client ID, and Client Secret.</p></li><li><p>Your Auth0 Authorization Server responds with an ID Token and Access Token (and optionally, a Refresh Token).</p></li><li><p>Your application can use the Access Token to call an API to access information about the user.</p></li><li><p>The API responds with requested data.</p></li></ol>

# 4. what is Implicit Flow with Form Post?
As an alternative to the Authorization Code Flow, OAuth 2.0 provides the Implicit Flow, which is intended for Public Clients, or applications which are unable to securely store Client Secrets. While this is no longer considered a best practice for requesting Access Tokens, when used with Form Post response mode, it does offer a streamlined workflow if the application needs only an ID token to perform user authentication.
# 5. what is Client Credentials Flow?
With machine-to-machine (M2M) applications, such as CLIs, daemons, or services running on your back-end, the system authenticates and authorizes the app rather than a user. For this scenario, typical authentication schemes like username + password or social logins don't make sense. Instead, M2M apps use the Client Credentials Flow

# 6. what is Device Authorization Flow?
With input-constrained devices that connect to the internet, rather than authenticate the user directly, the device asks the user to go to a link on their computer or smartphone and authorize the device. This avoids a poor user experience for devices that do not have an easy way to enter text. To do this, device apps use the Device Authorization

# 7. what is Resource Owner Password Flow?
Though we do not recommend it, highly-trusted applications can use the Resource Owner Password Flow, which requests that users provide credentials (username and password), typically using an interactive form. 