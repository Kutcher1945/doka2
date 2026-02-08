# CyberT

## Local/Production settings

1. For dev (local) purposes
   - Set db to sqlLite in DATABASES variable or configure local MySQL
   - Set redis channel's host to localhost in CHANNEL_LAYERS variable
2. For production purposes
   - Set db to sqlLite (MySQL is temporary not working) in DATABASES variable
   - Set redis channels's host to 'redis' in CHANNEL_LAYERS variable

## Run project locally

```
npm run dev
```
