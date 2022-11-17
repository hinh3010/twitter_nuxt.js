# prisma
* npx prisma init
    Next steps:
    1. Set the DATABASE_URL in the .env file to point to your existing database. If your database has no tables yet, read `https://pris.ly/d/getting-started`
    2. Set the provider of the datasource block in schema.prisma to match your database: postgresql, mysql, sqlite, sqlserver, mongodb or cockroachdb (Preview).
    3. Run prisma db pull to turn your database schema into a Prisma schema.
    4. Run prisma generate to generate the Prisma Client. You can then start querying your database.
* npx prisma db push
* npx prisma generate

# mẫu
```prisma 
model Post {
  id        Int      @id @default(autoincrement())
  createdAt DateTime @default(now())
  updatedAt DateTime @updatedAt
  title     String
  content   String?
  published Boolean  @default(false)
  viewCount Int      @default(0)
  author    User?    @relation(fields: [authorId], references: [id])
  authorId  Int?

  @@index([title, content])
}
```