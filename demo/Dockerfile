#INTEGRATE YOUR TOOL'S CONTAINER
FROM lcodo/demo_application:1.0

#---------- DO NOT EDIT BELOW HERE ------------------------------------------------------------# 
#INSTALL openVRE DEPENDENCIES
#Entrypoint requirements
RUN apt update -y && apt install -y  bindfs sudo
RUN apt-get update -qq ; apt-get install -y git vim python3-pip python3-venv
ARG DEBIAN_FRONTEND=noninteractive
COPY ./entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh

#OpenVRE runner installation
WORKDIR /home
RUN git clone --single-branch --branch dockerized https://github.com/inab/vre_template_agent.git
WORKDIR /home/vre_template_agent

RUN pip3 install --upgrade wheel
RUN pip3 install -r requirements.txt
RUN pip3 install --upgrade pip

#Adding your test files
COPY ./vre_template_agent/tests /home/vre_template_agent/tests
COPY ./vre_template_agent/VRE_Agent.py /home/vre_template_agent/agent
RUN chmod -R 777 /home/vre_template_agent
RUN  chmod -R a+rwx /home/vre_template_agent

#Execute entrypoint 
ENTRYPOINT ["/entrypoint.sh"]

