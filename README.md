## Lab description for hand in

Here's the public dashboard https://idguafi.github.io/mlfs-book/air-quality/

We aimed for an A grade and implemented the various models and pipelines as described in the lab description. For the C-level task, we implemented a model with and without lagged features. We utilised the versioning system in hopsworks for this. For the A-level task, we re-did the entire pipleine in a different branch so that we can show you both branches during the presentation. This required quite a lot of rewrites since everything was hardcoded for a single sensor previously. The system is now robust and can handle both single and multi sensor inference. You can see forecasts and hindcasts in the link. 

Authored by Joel Maharena and Sam Barati

# Run Air Quality Tutorial

See [tutorial instructions here](https://docs.google.com/document/d/1YXfM1_rpo1-jM-lYyb1HpbV9EJPN6i1u6h2rhdPduNE/edit?usp=sharing)
    # Create a conda or virtual environment for your project
    conda create -n book 
    conda activate book

    # Install 'uv' and 'invoke'
    pip install invoke dotenv

    # 'invoke install' installs python dependencies using uv and requirements.txt
    invoke install


## PyInvoke

    invoke aq-backfill
    invoke aq-features
    invoke aq-train
    invoke aq-inference
    invoke aq-clean



## Feldera


pip install feldera ipython-secrets
sudo apt-get install python3-secretstorage
sudo apt-get install gnome-keyring 

mkdir -p /tmp/c.app.hopsworks.ai
ln -s  /tmp/c.app.hopsworks.ai ~/hopsworks
docker run -p 8080:8080 \
  -v ~/hopsworks:/tmp/c.app.hopsworks.ai \
  --tty --rm -it ghcr.io/feldera/pipeline-manager:latest



