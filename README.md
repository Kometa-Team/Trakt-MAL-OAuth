# PMM_Auth

Perhaps you're running PMM in a docker or something where getting it into interactive mode to authentication trakt is a hassle.

This repo contains the scripts from [over here](https://github.com/chazlarson/Media-Scripts) wrapped up as a Flask app.

It's deployed at press time [here](https://pmm-auth-8e685ca9b226.herokuapp.com/)

You can review the code here if you're concerned about it saving credentials or the like.  I am profoundly uninterested in gaining access to your Trakt or MAL accounts.

You can run this on your own machine if you want to, of course.

### Usage

Operation should be pretty self-explanatory.

1. Enter client ID and secret.
2. For Trakt, if you didn't retrieve a PIN yourself less than ten minutes ago, click the button, and enter the PIN in the field.
3. For MyAnimeList, click the button to authenticate and get the required "localhost URL"
4. Click "Submit"
5. Copy and paste the result into your PMM config.

### Running it locally

You can run it in Docker or Python.

## Running in Docker

1. build the image with `docker build -t pmm-auth-image .`
2. run the container with `docker run --rm pmm-auth-image`
3. If you get a message complaining that something else is already running on port 5000, run the container with `docker run --rm -p 5001:5000 pmm-auth-image`
4. go to `http://127.0.0.1:5000` OR `http://127.0.0.1:5001`.
5. see instructions above

## Running in Python

1. Make sure you are running a recent Python [this was developed on Python 3.11]
2. Run these commands to create a virtual environment and install requirements.
   ```
   python3 -m venv ppm-auth-venv
   . ppm-auth-venv/bin/activate
   python -m pip install -r requirements.txt
   ```
3. run the script with `python app.py`
4. If you get a message complaining that something else is already running on port 5000, open `app.py` and change the 5000 on the last line to 5001; repeat step 3.
5. go to `http://127.0.0.1:5000` OR `http://127.0.0.1:5001`.
6. see instructions above

Docker or the already deployed version are recommended.