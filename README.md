## How to bring in a new agent?
Essentially, VRE will need thre elements, (1) a docker image for your agent (2) your application or workflow wrapped within a **VRE RUNNER**, and (2) **metadata** annotating it (*i.e.* input files requirements, descriptions). The following steps describe how to achieve it.

1. Clone https://github.com/inab/vre_template_agent_dockerized/​
2. Change in the Dockerfile the FROM image with the one for your agent, the rest leave it as it is​
3. Adjust the VRE_Agent.py of the vre_template_agent_dockerized repo and the tests folder​
4. Build the image with the modified Dockerfile​
5. Test with new image​

