FROM miykael/nipype_level2

RUN groupadd -g 48 boutiques && \
    useradd -m -s /bin/bash -N -u 48 boutiques -g boutiques

# 30 mars hackfest on monte une directory /rstp_data pour récupérer détarer le dataset et un autre pour mettre le code
RUN mkdir /rstp_data && \
    mkdir /rstp_code

# on copie le ginfizz_wrapper.sh, puis on va recuperer le pipeline de preprocess en python, enfin on récupère les 2 files from ginnipi/toolbox
COPY ./ginfizz_wrapper.sh ./ginfizz_config.py ./ginfizz_tools.py ./ginfizz_main.py ./ginfizz_preprocess.py ./ginfizz_bandpass.py ./ginfizz_aicha_ss_arima.py ./computations.py ./flow.py /rstp_code/

RUN chmod -R 777 /home/jovyan && \
    chmod -R 777 /rstp_data && \
    chmod -R 777 /rstp_code && \
    chmod -R 777 /opt

ENV PATH=${PATH}:/opt/conda/envs/python2/lib/python2.7/site-packages

ENTRYPOINT ["/bin/bash"]
