FROM ubuntu:22.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt update && apt install -y \
    xfce4 \
    xfce4-goodies \
    x11vnc \
    xvfb \
    novnc \
    websockify \
    wget \
    gnupg \
    supervisor \
    && apt clean

# Add Microsoft Edge repo
RUN wget -q https://packages.microsoft.com/keys/microsoft.asc -O- | apt-key add - && \
    echo "deb [arch=amd64] https://packages.microsoft.com/repos/edge stable main" \
    > /etc/apt/sources.list.d/microsoft-edge.list

RUN apt update && apt install -y microsoft-edge-stable

# Copy startup script
COPY ../start.sh /start.sh
RUN chmod +x /start.sh

EXPOSE 6080

CMD ["/start.sh"]
