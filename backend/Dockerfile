# 1. Base image so správnou verziou Node.js
FROM node:20-alpine

# Nastavenie produkčného prostredia
# ENV NODE_ENV=production

WORKDIR /app

# 2. Najprv kopírujeme len manifesty závislostí pre využitie Docker Cache
COPY package*.json ./

# Inštalujeme IBA produkčné závislosti
RUN npm install

# 3. Kopírujeme zdrojové kódy komponentu
COPY . .

# Bonus: Zabezpečenie, aby kontajner nebežal pod používateľom root
USER node


# 4. Deklarácia portu
EXPOSE $PORT

# 5. Automatické spustenie aplikácie
CMD ["npm", "start"]