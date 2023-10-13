FROM ubuntu:22.04

RUN apt update && apt full-upgrade -y

RUN apt update && apt install -y curl git nmap python3 python3-pip wget

RUN pip3 install aiohttp requests rich

WORKDIR /tools
RUN git clone https://github.com/nikitastupin/clairvoyance.git
RUN git clone -b v4.x https://github.com/doyensec/inql.git && cd /tools/inql && python3 setup.py install
RUN git clone https://github.com/dolevf/graphw00f.git
RUN git clone https://github.com/assetnote/batchql.git
RUN git clone https://github.com/dolevf/nmap-graphql-introspection-nse.git && cd /tools/nmap-graphql-introspection-nse && cp graphql-introspection.nse /usr/share/nmap/scripts
RUN git clone https://github.com/dolevf/graphql-cop.git && cd /tools/graphql-cop && pip3 install -r requirements.txt
RUN git clone https://github.com/nicholasaleks/CrackQL.git
RUN git clone https://github.com/commixproject/commix.git
RUN git clone https://github.com/RedSiege/EyeWitness.git
RUN wget "https://gitlab.com/dee-see/graphql-path-enum/-/jobs/artifacts/v1.1.1/raw/target/release/graphql-path-enum?job=build-linux"

