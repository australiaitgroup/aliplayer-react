# ALIPLAYER-REACT

React component wrapper for [aliplayer](https://player.alicdn.com).

Current version: 2.8.2 with additional components built by [aliplayer-components](https://github.com/aliyunvideo/AliyunPlayer_Web).

## Installation

```
npm i aliplayer-react-components-wrapper
```

## Usage

[![Edit aliplayer-react](https://codesandbox.io/static/img/play-codesandbox.svg)](https://codesandbox.io/s/floral-wind-5b507?fontsize=14)

```js
import React, { Component } from "react";
import ReactDOM from "react-dom";
import Player from "aliplayer-react";

const config = {
	source: "//player.alicdn.com/video/aliyunmedia.mp4",
	width: "100%",
	height: "500px",
	autoplay: true,
	isLive: false,
	rePlay: false,
	playsinline: true,
	preload: true,
	controlBarVisibility: "hover",
	useH5Prism: true,
	components: [
		{
			name: "RateComponent",
			type: Player.components.RateComponent,
		},
	],
};

class App extends Component {
	state = {
		instance: null, // player instance, e.g: player.stop();
	};
	render() {
		return (
			<div>
				<Player
					config={config}
					onGetInstance={(instance) => this.setState({ instance })}
					// Optional: custom cdn url
					// sourceUrl={'https://g.alicdn.com/de/prismplayer/2.8.2/aliplayer-min.js'}
				/>
			</div>
		);
	}
}

ReactDOM.render(<App />, document.getElementById("root"));
```
