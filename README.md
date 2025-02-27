# About Jarvis - An Intelligent AI Consciousness 🧠
Jarvis is a voice commanding assistant service in [Python 3.8](https://www.python.org/downloads/release/python-360/)
It can recognize human speech, talk to user and execute basic commands.

#### Requirements

* Operation system: **Ubuntu 20.04 (Focal Fossa)**
* Python Version: **3.8.x**


#### Assistant Skills 
*   **Opens a web page** (e.g 'Jarvis open youtube')
*   **Play music in Youtube** (e.g 'Jarvis play mozart')
*   **Increase/decrease** the speakers master volume (also can set max/mute speakers volume) ** (e.g 'Jarvis volume up!')
*   **Opens libreoffice suite applications (calc, writer, impress)** (e.g 'Jarvis open calc')
*   **Tells about something**, by searching on the internet (e.g 'Jarvis tells me about oranges')
*   **Tells the weather** for a place (e.g 'Jarvis tell_the_skills me the weather in London')
*   **Tells the current time and/or date** (e.g 'Jarvis tell me time or date')
*   **Set an alarm** (e.g 'Jarvis create a new alarm')
*   **Tells the internet speed (ping, uplink and downling)** (e.g 'Jarvis tell_the_skills me the internet speed')
*   **Tells the internet availability** (e.g 'Jarvis is the internet connection ok?')
*   **Tells the daily news** (e.g 'Jarvis tell me today news')
*   **Spells a word** (e.g 'Jarvis spell me the word animal')
*   **Creates a reminder** (e.g 'Jarvis create a 10 minutes reminder')
*   **Opens linux applications** (e.g 'Jarvis open bash/firefox')
*   **Tells everything it can do** (e.g 'Jarvis tell me your skills or tell me what can you do')
*   **Tells the current location** (e.g 'Jarvis tell me your current location')
*   **Tells how much memory consumes** (e.g 'Jarvis tell me your memory consumption)
*   **Tells users commands history** (e.g 'Jarvis tell me my history')
*   **Write/tell 'remember' and enable learning mode and add new responses on demand!** (e.g 'Jarvis remember')
*   **Clear bash console** (e.g 'Jarvis clear console')
*   **Has help command, which prints all the skills with their descriptions** (e.g 'Jarvis help')
*   **Do basic calculations** (e.g 'Jarvis (5 + 6) * 8' or 'Jarvis one plus one')
*   **Change settings on runtime** (e.g 'Jarvis change settings')

#### Assistant Features
*   **Asynchronous command execution & speech recognition and interpretation**
*   Supports **two different user input modes (text or speech)**, user can write or speek in the mic.
*   Answers in **general questions** (via call Wolfram API), e.g ('Jarvis tell me the highest building') 
*   **Change input mode on run time**, triggered by a phrase e.g 'Jarvis change settings')
*   Easy **voice-command customization**
*   Configurable **assistant name** (e.g 'Jarvis', 'Sofia', 'John' etc.) (change on run time supported)
*   **Log preview** in console
*   **Vocal or/and text response**
*   **Keeps commands history and learned skills** in MongoDB.'

## Getting Started
### Create KEYs for third party APIs
Jarvis assistant uses third party APIs for speech recognition,web information search, weather forecasting etc.
All the following APIs have free no-commercial API calls. Subscribe to the following APIs in order to take FREE access KEYs.
*   [OpenWeatherMap](https://openweathermap.org/appid): API for weather forecast.
*   [WolframAlpha](https://developer.wolframalpha.com/portal/myapps/): API for answer questions.
*   [IPSTACK](https://ipstack.com/signup/free): API for current location.
### Setup Jarvis in Ubuntu/Debian system
* Download the Jarvis repo locally:
```bash
git clone https://github.com/ggeop/Jarvis.git --branch master
```

**For Contribution**:
```bash
git clone https://github.com/ggeop/Jarvis.git --branch develop
```

*   Change working directory
```bash
cd Jarvis
```
*   Setup Jarvis and system dependencies:
```bash
bash setup.sh
```

*   Put the Keys in settings

**NOTE:** *For better experience, before you start the application you can put the free KEYs in the settings.py*

```bash
nano Jarvis/src/jarvis/jarvis/setting.py
```

### Start voice commanding assistant
![alt text](https://github.com/ggeop/Jarvis/blob/master/imgs/Jarvis_printscreen.PNG)

*   Start the assistant service:
```bash
bash run_jarvis.sh
```

### How to add a new Skill to assistant
You can easily add a new skill in two steps.
*   Create a new configuration SKILLS in **skills/registry.py**
```python
{ 
  'enable': True,
  'func': Skills.new_skill,
  'tags': 'tag1, tag2',
  'description': 'skill description..'
}               
```
*   Create a new skill module in **skills/collection**

### Decision Model
![alt text](https://github.com/ggeop/Jarvis/blob/master/imgs/desicion_model.png)

### Extract skill
The skill extraction implement in a matrix of [TF-IDF features](https://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.TfidfVectorizer.html) for each skill.
In the following example he have a dimensional space with three skills.
The user input analyzed in this space and by using a similarity metric (e.g cosine) we find the most similar skill.
![alt text](https://github.com/ggeop/Jarvis/blob/master/imgs/skill_space_desicion.png)

---

## Contributing
* Pull Requests (PRs) are welcome :relaxed:
* The process for contribution is the following:
    * Clone the project
    * Checkout `develop` branch and create a feature branch e.g `feature_branch`
    * Open a PR to `develop`
    * Wait for review and approval !!
    * `master` branch update and release is automated via [Travis CI/CD](https://app.travis-ci.com/github/ggeop/Python-ai-assistant)
* Try to follow PEP-8 guidelines and add useful comments!

## CI/CD Flow
![alt text](https://github.com/ggeop/Python-ai-assistant/blob/master/imgs/TravisFlow.png)

## 🔗 Related Projects

If you enjoy this virtual assistant, you might also be interested in my other AI-powered project: [DataDialogue](https://github.com/ggeop/DataDialogueLLM)

Transform the way you interact with databases through natural conversations! DataDialogue enables anyone to:

- 💬 **Query databases using natural language**
- 📊 **Get instant data visualizations**
- 🔍 **Explore data without SQL knowledge**
- 🤝 **Bridge the gap between data and business users**

<div align="center">
<div style="position: relative; display: inline-block; width: fit-content;">
  <a href="https://www.youtube.com/watch?v=breOr5o7r3Y" style="text-decoration: none;">
    <img src="https://github.com/ggeop/DataDialogueLLM/blob/main/media/imgs/data_dialogue_agent_responses.png" alt="DataDialogue Demo" width="600" style="display: block; border-radius: 8px; box-shadow: 0 4px 14px rgba(0, 0, 0, 0.1);"/>
  </a>
</div>
</div>

