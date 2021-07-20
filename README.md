# Jitsi Meet - Secure, Simple and Scalable Video Conferences

Jitsi Meet is an open-source (Apache) WebRTC JavaScript application that uses [Jitsi Videobridge](https://jitsi.org/videobridge) to provide high quality, [secure](https://jitsi.org/security) and scalable video conferences. Jitsi Meet in action can be seen at [here at the session #482 of the VoIP Users Conference](http://youtu.be/7vFUVClsNh0).

The Jitsi Meet client runs in your browser, without installing anything else on your computer. You can try it out at https://meet.jit.si.

Jitsi Meet allows very efficient collaboration. Users can stream their desktop or only some windows. It also supports shared document editing with Etherpad.

# Jitsi Localhost
> Jitsi's Developer Guide: https://jitsi.github.io/handbook/docs/dev-guide/dev-guide-web

You can use a localhost environment to test out changes with the jitsi code (from the [jitsi/jitsi-meet](https://github.com/jitsi/jitsi-meet) repo).

**Important:** This localhost setup is only suitable for a linux environment. If you're on Windows, refer to the Jitsi-Meet-Torture section and download WSL to use the Ubuntu terminal.

**Note:** In `webpack.config.js`, there is a function called `devServerProxyBypass` that has a conditional statement checking for directory paths. In order to use local files that you are editing, the file must be under the specified directories. They are: `css`, `doc`, `fonts`, `images`, `lang`, `sounds`, `static`, `libs`. (And those that end in `.wasm`).

**Important:** Make sure you're **NOT** root when performing these commands (unless `sudo` is present).

```
sudo apt-get install npm nodejs
git clone https://github.com/jitsi/jitsi-meet.git
```
Make sure your Node version is 12+ and npm version is 6+. Check with `node -v` and `npm version`. (Node v10.19.0 seems to work fine actually).

The git version used at time of writing was v2.25.1.

```
cd /path/to/jitsi-meet
npm install

make
```

To launch localhost, type
```
make dev
```
After the code has been compiled and the messages stop, your site should be at https://localhost:8080

**Note:** By default the backend deployment used is alpha.jitsi.net. You must set up your environment to use the local files instead of getting served from the default backend. Otherwise you will not see any changes reflected in your localhost even after editing files such as `interface_config.js`.

Whenever you make changes to your code, run `make dev` to start up the localhost.
