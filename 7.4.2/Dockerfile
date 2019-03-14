# ipywidgets 7.4.2 on python3.6
FROM python:3.6
MAINTAINER damien.leprovost@clevy.io

# Install nodejs and deps
RUN curl -sL https://deb.nodesource.com/setup_11.x | bash - \
  && apt install -y nodejs \
  && npm i -g webpack@4.29.6 webpack-cli@3.2.3 fs-extra@7.0.1
# Install Jupyter Lab, ipywidgets and deps
RUN pip install ipywidgets==7.4.2 jupyterlab==0.35.4 \
  && jupyter nbextension enable --py widgetsnbextension \
  && jupyter labextension install @jupyter-widgets/jupyterlab-manager@0.38

WORKDIR /app

EXPOSE 8888

# Run Jupyter Lab on port 8888
CMD ["jupyter", "lab", "--ip=0.0.0.0", "--no-browser", "--allow-root", "--NotebookApp.custom_display_url=http://localhost:8888"]
