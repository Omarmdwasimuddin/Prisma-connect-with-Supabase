## Prisma Connect with Supabase for NextJS

### Prisma Dependencies Install

#### Dev dependencies:
```terminal
npm install prisma tsx @types/pg --save-dev
```

#### Production dependencies:
```terminal
npm install @prisma/client @prisma/adapter-pg dotenv pg
```
---

### Prisma Initialize
```terminal
npx prisma init 
```
---

### Visit supabase.com --->go: dashboard --->click: New project --->set Project name & Database password--->click: Create new project
![](https://imgur.com/Tqumq5m.png)

### click: Connect --->Select: ORM ---> copy: .env.local ---> paste: .env
![](https://imgur.com/LPN7bu9.png)
![](https://imgur.com/PnewSZ3.png)

### Modify--->prisma.config.ts and schema.prisma
![](https://imgur.com/jdzIgQD.png)
![](https://imgur.com/mzSubgW.png)

### Migration and prisma client generated
```terminal
npx prisma migrate dev --name init
```
```terminal
npx prisma generate
```
---

#### Migration successfull!!!
![](https://imgur.com/dhgM3BI.png)
