# Reactjs-Quiz-app
```
version: "3"
services:
  frontend:
    image: frontend:01
    ports:
      - "8080:8080"
    networks:
      - front-tier
  backend: 
    image: backend:01
    ports:
      - "3000:3000"
    networks:
      - front-tier
      - back-tier
    depends_on:
      - mongodb
  mongodb:
    image: mongo:latest
    ports:
      - "27017:27017"
    networks:
      - back-tier
networks:
  front-tier:
  back-tier:
```
