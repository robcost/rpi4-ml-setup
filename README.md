# rpi4-ml-setup

Install JupyterHub, run as a service, and default to Jupyter Lab.

```
sudo apt-get update
sudo apt-get install nano
sudo apt-get install python3-matplotlib python3-scipy
sudo -H pip3 install notebook jupyterhub
jupyterhub --generate-config
sudo mv jupyterhub_config.py /root

sudo su -
nano /root/jupyterhub_config.py
# update: c.JupyterHub.default_url = '/user/:username/lab'

sudo systemctl daemon-reload
sudo systemctl start jupyterhub
sudo systemctl enable jupyterhub
sudo systemctl status jupyterhub.service
sudo -H pip3 install jupyterlab
sudo jupyter serverextension enable --py jupyterlab --system
sudo -H pip3 install jupyterlab-git
sudo jupyter lab build --dev-build=False --minimize=False
sudo su -

sudo systemctl status jupyterhub.service
 ```
 
 