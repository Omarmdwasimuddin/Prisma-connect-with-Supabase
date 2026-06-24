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

### Create Inistance for API
![](https://imgur.com/0xO90A5.png)
```code
import { PrismaClient } from "@/app/generated/prisma/client";
import { PrismaPg } from "@prisma/adapter-pg";

const globalForPrisma = global as unknown as { 
    prisma: PrismaClient;
 };

 const adapter = new PrismaPg({
    connectionString: process.env.DATABASE_URL,
 });

 const prisma = globalForPrisma.prisma || new PrismaClient({ adapter, });

 if (process.env.NODE_ENV !== "production") globalForPrisma.prisma = prisma;

 export default prisma;
```
