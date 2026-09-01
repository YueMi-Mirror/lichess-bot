ARG VARIANT
FROM python:3$VARIANT
LABEL org.opencontainers.image.authors="Lichess Bot Devs <lichess.bot.devs@gmail.com>"
LABEL org.opencontainers.image.description="A bridge between Lichess API and chess engines"
LABEL org.opencontainers.image.source="https://github.com/lichess-bot-devs/lichess-bot"
LABEL org.opencontainers.image.documentation="https://github.com/lichess-bot-devs/lichess-bot/wiki/How-to-use-the-Docker-image"
LABEL org.opencontainers.image.title="lichess-bot"
LABEL org.opencontainers.image.licenses="AGPL-3.0-or-later"

ENV LICHESS_BOT_DOCKER="true"
ENV PYTHONDONTWRITEBYTECODE=1

WORKDIR /lichess-bot

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY lichess-bot.py .
COPY lib/ ./lib/
COPY extra_game_handlers.py .
COPY homemade.py .
COPY config/ ./config/

CMD python3 lichess-bot.py ${OPTIONS}
