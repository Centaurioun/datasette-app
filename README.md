# Datasette.app

An Electron app that wraps [Datasette](https://datasette.io/).

The app consists of two parts: the Electron app, and a custom Datasette plugin called datasette-app-support.

It is not yet packaged with an installer. You can preview the app like so:

    # Clone the repo
    git clone https://github.com/simonw/datasette.app
    cd datasette.app
    
    # Start a Python virtual environment
    pipenv shell
    pip install datasette-app-support/.
    
    # Confirm the custom datasette is on the path
    which datasette
    # If that doesn't show the datasette.app one, hit Ctrl+D then run 'pipenv shell' again
    
    # Install Electron dependencies and start it running:
    npm install
    npm start

To run the plugin tests:
    
    pip install 'datasette-app-support/.[test]'
    pytest

To run the Electron tests:

    npm test

The Electron tests may leave a `datasette` process running. You can find the process ID for this using:

    ps aux | grep xyz

Then use `kill PROCESS_ID` to terminate it.
