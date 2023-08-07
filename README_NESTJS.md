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

9. `npx prisma migrate dev`   ==> run migrate cho trường hợp chung chỉ nên dùng cho devlopment
10. `npx prisma migrate deploy` ==> applied migrate cho database đã có ==> nên dùng cho production


11. prisma migrate reset ==> Apply pending migrations to the database in production/staging

12. Generate file in nestjs: `nest g resource [users]`