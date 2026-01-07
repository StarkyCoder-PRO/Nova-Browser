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
    git \
    && apt clean

RUN chmod +x /start.sh

EXPOSE 6080

CMD ["/start.sh"]
