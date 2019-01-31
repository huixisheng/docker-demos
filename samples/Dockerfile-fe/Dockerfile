FROM node:8.11.3-slim

MAINTAINER huixisheng <huixisheng@gmail.com>

# http://mirrors.ustc.edu.cn/help/dockerhub.html
# https://segmentfault.com/a/1190000007587170
COPY ./sources.list /etc/apt/sources.list

RUN apt-get clean \
  && rm -rf /var/lib/apt/lists/* \
  && apt-get update \
  # https://hub.docker.com/r/1maa/debian/~/dockerfile/
  && DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends \
    --assume-yes apt-utils \
  && apt-get install -y git zsh vim 

# https://github.com/kkarczmarczyk/docker-node-yarn/blob/master/4.3.2/Dockerfile
# Global install yarn package manager
RUN apt-get install -y curl apt-transport-https && \
    curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - && \
    echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list && \
    apt-get update && apt-get install -y yarn

#RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - 
# RUN apt-get install -y yarn

# RUN curl -o yarnpkg.gpg.pub https://raw.githubusercontent.com/yarnpkg/releases/gh-pages/debian/pubkey.gpg
RUN wget -qO- https://raw.githubusercontent.com/creationix/nvm/v0.33.5/install.sh | bash
RUN wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | zsh || true

# china mirrors
RUN true \
  # npm china mirrors
  # && npm config set registry https://registry.npm.taobao.org \
  && npm config set electron_mirror https://npm.taobao.org/mirrors/electron/ \
  && npm config set phantomjs_cdnurl https://npm.taobao.org/dist/phantomjs \
  && npm config set chromedriver_cdnurl https://npm.taobao.org/mirrors/chromedriver \
  && npm config set disturl https://npm.taobao.org/dist \
  && npm config set node_inspector_cdnurl https://npm.taobao.org/mirrors/node-inspector \
  && npm config set nvm_nodejs_org_mirror https://npm.taobao.org/mirrors/node -g \
  && npm config set sass_binary_site https://npm.taobao.org/mirrors/node-sass \
  && yarn config set registry https://registry.npm.taobao.org \
  && yarn config set electron_mirror https://npm.taobao.org/mirrors/electron/ \
  && yarn config set phantomjs_cdnurl https://npm.taobao.org/dist/phantomjs \
  && yarn config set chromedriver_cdnurl https://npm.taobao.org/mirrors/chromedriver \
  && yarn config set disturl https://npm.taobao.org/dist \
  && yarn config set node_inspector_cdnurl https://npm.taobao.org/mirrors/node-inspector \
  && yarn config set sass_binary_site https://npm.taobao.org/mirrors/node-sass -g \
  && yarn config set nvm_nodejs_org_mirror https://npm.taobao.org/mirrors/node -g \
  # debian china mirrors
  && sed -i 's/deb.debian.org/mirrors.ustc.edu.cn/g' /etc/apt/sources.list \
  # timezone to china
  && ln -sf /usr/share/zoneinfo/PRC /etc/localtime \
  # just for fun
  && echo 'ZSH_THEME="random"' > ~/.oh-my-zsh/custom/custom.zsh \
  # This loads nvm
  && echo 'export NVM_DIR="$HOME/.nvm"' >> ~/.oh-my-zsh/custom/custom.zsh \
  && echo '[ -s "$NVM_DIR/nvm.sh" ] && source "$NVM_DIR/nvm.sh"' >> ~/.oh-my-zsh/custom/custom.zsh

# RUN npm install --registry=https://registry.npm.taobao.org -g \
#   cnpm \
#   anywhere \
#   @vue/cli \
#   webpack \
#   vuepress

RUN mkdir /workspace

WORKDIR /workspace

VOLUME /workspace

EXPOSE 8080

CMD ["zsh"]