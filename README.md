NodeJS nejde na "workstation" nainstalovat protože prý nemá pravá. Nevidím žádnou portable verzi Dockeru. Má "workstation" je neskutečně pomalá, takže se vše instaluje moc dlouho. Tady je alespoň jak udělat webovou stránku se jménem: 

https://github.com/Zer0x739/docker/blob/dc299eae1813e669916a3aeeff7ca494902f0026/index.js#L1-L11

Tady je kód pro vytvoření 'Dockerfile' v Dockeru:

```
FROM node:14-alpine

WORKDIR /app

COPY package.json package-lock.json ./
RUN npm install

COPY . .

EXPOSE 3000
CMD [ "npm", "start" ]
```
Tady je příkaz na vytvoření image: 

```
docker build -t <obrazek>
```
Příkaz pro spuštění kontejneru: 

```
docker run -p 3000:3000 <jméno vašeho obrazu>
```
Webovou stránku s vypsaným jménem otevřeme vyhledáním této adresy v prohlížeči:

```
http://localhost:3000
```
