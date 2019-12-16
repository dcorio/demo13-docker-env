FROM dubheit/odoo-docker-image:13.0

USER root

# This will install the addons's python dependencies
COPY odoo-extra-requirements.txt odoo-extra-requirements.txt
RUN pip3 install -r odoo-extra-requirements.txt

USER odoo

COPY odoo_conf.yaml odoo_conf.yaml
RUN python3 scripts/generate_odoo_conf.py odoo.cfg.j2 odoo_conf.yaml > /opt/odoo/etc/odoo.cfg

RUN rm -rf /opt/odoo/.ssh
