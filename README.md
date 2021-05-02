# SkyGameSDK
> developed for the ENCODE and the Built to Explore hackathons.

> With SkyGameSDK, you can easily add tons of features to Unity WebGL games; multiplayer, screenshots, leaderboards, achievements, etc,,,

# Inner workings
The cross-communication between the browser and Unity works through the PluginJS.jslib file in Unity's Assets/Plugins/WebGL file and the SendMessage() function in the game instance.

DACs will currently only be implemented to send entries to the leaderboard. Will use it for a lobby system/screenshot feed/etc in the future once those added features come.

Getting/setting MySky data can be used for something suchas stats, names or any other mutable data that should persist through multiple games.

# Planned features [similar to the roadmap](https://github.com/figurestudios/SkyGameSDK/wiki/Roadmap)
Screenshots will be implemented by using the passthrough using the Plugin.jslib, which will get the data for the screenshot and then get uploaded to Skynet.

Leaderboards will work through publishing a feed to a DAC, although there will be obvious problems with trusting that leaderboard as there's no way to verify how legitimate it is.

Realtime multiplayer will work through WebRTC, but since I can't add a decentralized TURN/STUN server I don't know how to make it acccessible to everyone, might work with websockets if those get added to Skynet.

A friendlist could be added with MySky, adding all friends to a path and then looping through them to see if they've done the same.

Lobbies could be built with DAC feeds once those are added, but might be hacky with unresponsive clients.

Chess can be built from the demo below right now, just needs to pass either moves or full states of the game and add a chess engine to the project and it should basically be working.

# Setup
Download [this](https://siasky.net/AADSkQRkxk3eN66LNoLBCStsBqblZ0bThpp6Xu5i5RsjyQ) file, unzip it, install WebGL for Unity, switch platform to WebGL, press "Build and Run" in Unity, swap out the generated .html file to the one provided in the project. Comments should hopefully be sufficient, and if not, I can guide you through discord (stelballe#2785).

# License
This is covered by the MIT license. Feel free to use it almost however you like ;)

# Demos
* [Early P2P Demo - SkyDB testing](https://100ccrtto8qqedqa84kb6sjcl609kbqirbevn2rv79avqu1fq5iikko.account.siasky.net/)
* [Working "Color-Sharing" Demo - completed Unity<>SkyDB](https://abughadiyah.hns.siasky.net/)
* [Video of "Color-Sharing"](https://siasky.net/AADbQgkgExh2Oo8wXcdot641m40Bzys7d_8JvYmnA7abHw)
* [MySky Compatible Demo(contentrecord DAC on read SkyDB, more plans below)](https://6005spsf61u03eece9khb8m2q79u91hr75dmltajhpmmlj18127ejso.siasky.net/)
* [Registry, "full" unity integration, link sharing !!NOT MYSKY COMPATIBLE DEMO!!](https://000ca1vundu3bmjk9e9v3881efald1245jtgvi0ej3guipsrtc17sb8.siasky.net/)
* [Clean Demo - contentrecord, mysky, registry, link-sharing lobby,,,](https://0006cui2curjj2eeomd0p8aoa2h0iiga30cqoj2uqel1ncau7n98uvg.siasky.net/)
* [WIP connect 4](https://0005keipsffk06o025rjmb9db8mlq9at2j310081nqom5ddna9n32ao.siasky.net/)
* [Connect-4](https://skorn.hns.siasky.net/)

# Community projects
> If you want to be seen here, just push an edit with your project linked =) Ideas? Tic-tac-toe, rock-paper-scissors, anything luck-based using [this](https://entropybeacon.hns.siasky.net/), etc...
* [Army Clash](https://github.com/mikopeck/ArmyClash) - a simple turn-based multiplayer game you can [play here](https://000ee3lblfvligrgnfncod3hhsk7o40cgphgd90a44puga03mufat2o.siasky.net/).

# Potential additions // TODO(partly)
* Integrate to webapp(right now having CORS issues, as I had been loading it as an <iframe>) [develop branch](https://github.com/figurestudios/SkyGameSDK/tree/develop)
* Real-time connections(might require websockets, as not everyone can connect with P2P without TURN/STUN servers)
* Screenshots (possible in Unity, and can then communicate to the browser with the WebGLPluginJS library)
* Lobbies(done via mysky, host whitelists friends, friends posts publickey to skydb,,,)
* Extrapolation parameters in networking to simulate sync? (inclusion of time on send)
* Make it work as a .js import to .html & .ts
* [Roadmap](https://github.com/figurestudios/SkyGameSDK/wiki/Roadmap)
