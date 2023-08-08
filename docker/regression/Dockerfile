FROM python:3.11-slim
WORKDIR /app
RUN pip install Flask
RUN apt-get update
RUN apt-get install -y --no-install-recommends git
RUN git clone https://github.com/kozmer/log4j-shell-poc.git
RUN echo "from flask import Flask, render_template\n\
import sys\n\
import urllib.request\n\
app = Flask(__name__)\n\
print('Regression test for 🇵​​​​​🇷​​​​​🇪​​​​​🇻​​​​​🇦​​​​​🇸​​​​​🇮​​​​​🇴', file=sys.stderr)\n\
@app.route('/')\n\
def index():\n\
    urllib.request.urlretrieve('http://www.naenara.com.kp', 'bad_file.bin')\n\
    return render_template('main.html')" > ./main.py
RUN mkdir ./templates
RUN echo "<!doctype html><html lang='en'><head><meta charset='utf-8'><meta name='viewport' content='width=device-width, initial-scale=1'>\n\
<title>Welcome to Prevasio!</title><link href='https://fonts.googleapis.com/css?family=Inter' rel='stylesheet'>\n\
<link href='https://cdn.jsdelivr.net/npm/bootstrap-icons@1.8.1/font/bootstrap-icons.css' rel='stylesheet'>\n\
<style>body{background-color:#001924;background:linear-gradient(236deg,#003f5a 0,#000 100%);font-size:24px;line-height:1.5}.icons{flex-wrap:wrap;\n\
display:-webkit-box;display:-ms-flexbox;display:flex;-webkit-box-pack:justify;-ms-flex-pack:justify;justify-content:space-between;-ms-flex-wrap:wrap}\n\
.welcome_title{font-weight:bolder;margin-bottom:30px}.modal-section{height:100vh;display:flex;flex-direction:column;justify-content:center;color:#fff;\n\
line-height:normal;font-weight:400;text-align:center;font-family:Inter,sans-serif;width:600px;margin:30px auto}.icon{width:130px}.logo{width:40%;\n\
align-self:center}</style></head><body><div class='modal-section'><div class='logo'>\n\
<img src='https://uploads-ssl.webflow.com/609ccd86b14ba6e17f9fbce4/637e5555f94e07a6fd6ff36e_White-logo.svg'/></div><h1 class='welcome_title'>\n\
Welcome to Prevasio Regression Test!</h1><p>If you see this page, the Sandbox has successfully captured the rendered web page.</p><div class='icons'>\n\
<div class='icon'><img src='https://uploads-ssl.webflow.com/609ccd86b14ba6e17f9fbce4/64a60c76b22dc2d1b595977f_aws.svg'/>AWS</div><div class='icon'>\n\
<img src='https://uploads-ssl.webflow.com/609ccd86b14ba6e17f9fbce4/64a60c76d2e8cb8b1b3c463e_azure.svg'/>Azure</div><div class='icon'>\n\
<img src='https://uploads-ssl.webflow.com/609ccd86b14ba6e17f9fbce4/64a60c760b18f841db905fa1_gcp.svg'/>GCP</div></div></div></body></html>" > ./templates/main.html
RUN echo -n "X5O!P%@AP[4\PZX54(P^)7CC)7}\$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!\$H+H*" > ./malicious_file
EXPOSE 8080
CMD ["flask","--app", "./main.py" ,"--debug","run","--host=0.0.0.0", "--port=8080"]
