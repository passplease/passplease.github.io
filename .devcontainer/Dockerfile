FROM mcr.microsoft.com/devcontainers/jekyll:2-bullseye

WORKDIR /website

EXPOSE 4000

RUN git clone https://github.com/passplease/Chirpy-Template ./

RUN apt-get update && apt-get install -y curl \
    && curl -fsSL https://deb.nodesource.com/setup_20.x | bash - \
    && apt-get install -y nodejs \
    && npm install -g @google/gemini-cli \
    && npm install -g @qwen-code/qwen-code@latest \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

RUN bundle config mirror.https://rubygems.org https://gems.ruby-china.com \
    && bundle install \
    && npm config set registry https://registry.npmmirror.com \
    && npm install \
    && npm run build