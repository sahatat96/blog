---
title: 'Docker Compose ဖြင့် Multi-Container Apps တည်ဆောက်ခြင်း'
description: 'Docker Compose ကို အသုံးပြုပြီး Application များစွာကို တစ်ပြိုင်နက် Run နည်း'
pubDate: 'Mar 21 2026'
heroImage: '../../assets/blog-placeholder-5.jpg'
category: 'Docker'
---

## Docker Compose ဆိုတာဘာလဲ

Docker Compose ဆိုတာ Container တွေ အများကြီးကို YAML ဖိုင်တစ်ခုတည်းနဲ့ သတ်မှတ်ပြီး တစ်ပြိုင်နက် Run နိုင်အောင် လုပ်ပေးတဲ့ Tool ပါ။

### docker-compose.yml ဥပမာ

```yaml
version: '3.8'
services:
  web:
    build: .
    ports:
      - "3000:3000"
  db:
    image: postgres:15
    environment:
      POSTGRES_PASSWORD: secret
```

### အသုံးဝင်တဲ့ Commands များ

```bash
docker-compose up -d
docker-compose down
docker-compose logs -f
```

တကယ့် Project တွေမှာ Backend, Database, Redis အစရှိတဲ့ Service တွေကို Docker Compose နဲ့ တစ်ခါတည်း စီမံခန့်ခွဲလိုက်တာက အချိန်ကုန်သက်သာစေပါတယ်။
