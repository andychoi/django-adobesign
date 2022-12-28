
# Django Adobe sign demo/test

`django-adobesign` is a Django application for Adobe EchoSign's digital signature.

It implements `django-anysign`_ API.


.. _`django-anysign`: https://pypi.org/project/django-anysign/

- Check account authentication region: https://wiki.smartsimple.com/wiki/Adobe_Sign
- Setup Adobe sign : https://autoever.na2.echosign.com/account/accountSettingsPage#pageId::API_APPLICATIONS
  - account type: self
  - oauth scope: user login, agreement send/read/write 
  - test : redirect URI https://localhost:8000/token

# Run with SSL
python -m venv .venv && source .venv/bin/activate
python -m pip install -r requirements.txt

python manage.py runsslserver


# Browser
- create setting: https://localhost:8000/
 - root uri: https://secure.na2.echosign.com
 - application id
 - secret
 
https://localhost:8000/token
https://localhost:8000/signature

## Markdown editor
https://itsfoss.com/online-markdown-editors/
https://github.com/marktext/marktext



# how to create pdf and upload
https://experienceleague.adobe.com/docs/document-services/tutorials/acrobatsign/signapi.html?lang=

https://pypi.org/project/mdpdf/
https://pandoc.org/

issue in table format...
pandoc example.md -o example.pdf --from markdown+pipe_tables

pandoc example.md -s -o example.pdf -f markdown-simple_tables-multiline_tables-grid_tables+pipe_tables


# Render pdf and send email

from easy_pdf.rendering import render_to_pdf
...
post_pdf = render_to_pdf(
        'post/post_pdf.html',
        {'any_context_item_to_pass_to_the_template': context_value,},
)
...
msg.attach('file.pdf', post_pdf, 'application/pdf')

Below works to generate table in HTML
$ markdown2 --extras tables example.md > example.html

README: https://www.youtube.com/watch?v=nUldCPt78s0&ab_channel=AdobeDevelopers