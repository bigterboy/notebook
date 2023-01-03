# NOTEBOOK

> NOTE FOR NESTJS

1. When add new data, need to use this to create new script sql
`npx prisma migrate dev` and `yarn service:dev:restart` to start server again

Can use `npx prisma migrate dev` for init sql file


2. Add some user before run server
`prisma db seed` add user, .... to database

3. Generate
`nest g module post`  ==> create module
`nest g controller post` ==> create controller