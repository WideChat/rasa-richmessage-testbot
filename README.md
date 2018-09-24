## Rasa Richmessage testbot

## Installation

* Install python3.6 along with its dev tools if not already present on the system

* Create a virtual env with python3.6
```sh
virtualenv -p python3.6 venv
```

* Activate the venv and Install requirements
```sh
source venv/bin/activate
pip install -r requirements.txt
```

* Download and link spacy en
```
python -m spacy download en_core_web_md
python -m spacy link en_core_web_md en
```

* Create a bot user and update the rocketchat credentials in `credentials.yml`

* WebHook

  * In RC go to **Administration > New Integration > Outgoing webhook**. Create a webook with following configuration.

```
Event Trigger: Message Sent
Enabled: True
Channel: @bot_username
URLs: http://localhost:5055/webhooks/rocketchat/webhook
Post as: bot_username
```

* Start the action endpoint
```
make action-server
```

* Start the rasa server
```
make run
```

