
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

# how to create pdf and upload
https://experienceleague.adobe.com/docs/document-services/tutorials/acrobatsign/signapi.html?lang=en