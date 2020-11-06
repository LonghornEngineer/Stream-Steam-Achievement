# Stream-Steam-Achievement

Need to implement this node server to utilize the steam api and add the following function to the server.js

https://codepen.io/johnchristopherjones/post/how-do-i-use-the-steam-api-in-my-web-app

app.get('/steam/:userid/:appid/achievements', function(httpRequest, httpResponse) {
    // Calculate the Steam API URL we want to use
    var url = 'http://api.steampowered.com/ISteamUserStats/GetPlayerAchievements/v0001/' +
        '?key=yoursteamapikeyhere&appid=' + httpRequest.params.appid +
        '&steamid=' + httpRequest.params.userid;
    request.get(url, function(error, steamHttpResponse, steamHttpBody) {
        httpResponse.setHeader('Content-Type', 'application/json');
        httpResponse.send(steamHttpBody);
    });
});