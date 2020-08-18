![sample pendulum video](assets/sample.gif)
# Double Pendulum Twitterbot
Feel free to follow the bot on [Twitter](https://twitter.com/DatSwingyBoi)!


## Installing / Initial Configuration

Before anything else, make sure to `pip install -r requirements.txt` the project so
that the Python scripts work fine.

Afterwards, make a copy of `configSAMPLE.json` and rename it to `config.json`. Inside `config.json`, set `DOWNLOADS_FOLDER` to be the path to your "Downloads" folder.

If you'd also like to upload the `.mp4` files to Twitter, then apply for a [Twitter Developer](https://developer.twitter.com/en/apply-for-access) account and follow the 
instructions on the website. You need this so you can generate your API tokens.

Once you've generated your tokens, add them into `config.json` as `CONSUMER_KEY`, `CONSUMER_SECRET`, `API_KEY`, and `API_SECRET`. 

However, if you don't want to do any of the Twitter stuff then you don't need to do anything besides installing `requirements.txt` and adding `DOWNLOADS_FOLDER`.



## Getting Started

There are really just two files that you're going to be interacting with: `automate.py` and `posttweet.py`.

* `automate.py` records 15 seconds of swinging double pendulums and then exports the final video into `output.mp4`. Afterwards, it puts the parameters used to generate the pendulums into `p5parameters.txt`. 
When it's done rendering, it automatically opens your media player so you can watch `output.mp4`. It also asks if you'd like to render another one, in which case
it deletes the existing `output.mp4` and `p5parameters.txt` and then renders another clip.

* `posttweet.py` takes the `output.mp4` and `p5parameters.txt` files that were generated by `automate.py` and uses the API tokens in `config.json` to upload `output.mp4`, with `p5parameters.txt` as the caption.

WARNING: since `posttweet.py` relies on files that `automate.py` generates, you should run `automate.py` at least once before running `posttweet.py`.


## Credits

* [CCapture.js](https://github.com/spite/ccapture.js/)
* [FFmpeg](https://ffmpeg.org/)


## Contributing

If you'd like to contribute, please fork the repository and use a feature
branch. Pull requests are warmly welcome!


## Licensing

The code in this project is licensed under MIT license.