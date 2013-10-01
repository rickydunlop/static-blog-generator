# Python static blog generator


## Installation
This assumes that you have [virtualenv](http://www.virtualenv.org/en/latest/) and [virtualenvwrapper](http://virtualenvwrapper.readthedocs.org/en/latest/) installed

    git clone https://github.com/rickydunlop/static-blog-generator.git $NEW_PROJECT_NAME
    cd $NEW_PROJECT_NAME

    mkvirtualenv --no-site-packages $NEW_PROJECT_NAME
    pip install -r requirements.txt


## Building the static site
The generator script will create a folder called `build` in the project's root directory.

This will contain all the static assets that you can then deploy to your web server.

Run the build script with the following command

    python generator.py build