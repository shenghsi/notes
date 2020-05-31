### venv
``` bash
python3 -m venv project_env
source project_env/bin/activate
pip list 
pip install packages
pip freeze > requirements.txt
deactivate
rm -rf project_env/

python3 -m venv project/venv
source project/venv/bin/activate
pip intall -r requirements.txt

# venv that can access system packages
python3 -m venv venv --system-site-packages
source venv/bin/activate
pip list
pip list --local
```
