
# My resume

My resume: [http://xavierguihot.com/jsonresume-theme-stackoverflow/](http://xavierguihot.com/jsonresume-theme-stackoverflow/)

This project is a fork of [https://github.com/francescoes/jsonresume-theme-stackoverflow](https://github.com/francescoes/jsonresume-theme-stackoverflow) by Francesco Esposito.

His project is a resume template (inspired by stackoverflow website's theme) for json resumes whose format is provided at [https://github.com/jsonresume](https://github.com/jsonresume).

So my work here has just been to fork Francesco Esposito's resume template, to create the resume.json file which contains data related to my resume, to find out how to properly generate the static index.html of the resume and for hosing, to set it as the github page of this repository. I've also slightly modified a few parts of the resume template to my preferences.

# index.html update

    # Create whatever virgin folder
    npm install git+https://git@github.com/xavierguihot/jsonresume-theme-stackoverflow
    cd node_modules
    npm install -g resume-cli # or sudo npm install puppeteer --unsafe-perm=true --allow-root` and then `sudo npm install resume-cli --unsafe-perm=true --allow-root`
    rm -rf jsonresume-theme-stackoverflow-modified
    git clone https://github.com/xavierguihot/jsonresume-theme-stackoverflow.git
    cd jsonresume-theme-stackoverflow
    resume serve # or node_modules/resume-cli/index.js serve
    * this has the effect to create the new static index.html
    cp public/index.html .
    * Then commit and push

# Export to crappy PDF

The PDF translation isn't perfect:

    sudo apt-get install wkhtmltopdf
    resume export resume-paper.html -t stackoverflow
    wkhtmltopdf resume-paper.html resume.pdf
    xdg-open resume.pdf
