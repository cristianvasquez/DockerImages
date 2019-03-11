# EYE Server image, based on EYE Server by Ruben Verborgh
# http://eulersharp.sourceforge.net/
FROM bdevloed/eye:latest
MAINTAINER Boris De Vloed <boris.devloed@agfa.com>

# Install latest nodejs and EYEServer
RUN curl -fsSL https://deb.nodesource.com/setup_4.x | bash - && \
    apt-get install -qy nodejs && \
    apt-get purge -qy lsb-release && \
    apt-get -qy autoremove && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

#RUN npm -g install https://github.com/RubenVerborgh/EyeServer/tarball/master
RUN npm -g install eyeserver

EXPOSE 8000
CMD ["8000"]

ENTRYPOINT eyeserver
