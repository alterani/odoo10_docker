FROM odoo10

ONBUILD COPY ./addons/l10n-italy /mnt/extra-addons

USER root

#Installa PyXB necessario per fattura PA
RUN pip install PyXB==1.2.5 --user

COPY ./odoo.conf /etc/odoo/
RUN chown odoo /etc/odoo/odoo.conf
RUN chown -R odoo /mnt/extra-addons

USER odoo

        


#Installa gli addons
#ADD ./addons/l10n_it_fatturapa /mnt/extra-addons/l10n_it_fatturapa
#ADD ./addons/l10n_it_fatturapa_in /mnt/extra-addons/l10n_it_fatturapa_in
#ADD ./addons/l10n_it_fatturapa_out /mnt/extra-addons/l10n_it_fatturapa_out
#RUN chown -R odoo /mnt/extra-addons


# ...... SERVE PER INSTALLARE Less MA NON STA FUNZIONANDO .....
# RUN curl -sL https://deb.nodesource.com/setup_10.x | bash -
# RUN apt-get install -y nodejs
# RUN npm install -g less

# Per installare git sulla macchina
# RUN apt-get update && apt-get install -y git

# USER odoo


#RUN set -x; \
#        apt-get update \
#        && apt-get install -y --no-install-recommends \
#            git \
#        && git clone -b 10.0 https://github.com/OCA/l10n-italy.git \
#        && mv l10n-italy /mnt/extra-addons
