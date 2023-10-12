# Postgresql Setup

### Postgresql is a database, PGADMIN4 is the UI we use to visualize it.

Download [PGADMIN4 here](https://www.postgresql.org/). After downloading PGADMIN4 for your OS, install it. Once installed, launch PGADMIN4.

# Prisma Setup

### Prisma is used for building out schemas for different databases

We will setup our Prisma Schema inside our backend code. Enter your backend directory from the command line and run `npx prisma init` to add Prisma to your project. After initialized, a Prisma folder will be created with a _schema.prisma_ file. Inside this file is where you will build out the [schema for you data](https://www.prisma.io/docs/concepts/components/prisma-schema). To help visualize your schema [checkout this VS Code extension](https://marketplace.visualstudio.com/items?itemName=Prisma.prisma) for syntax highlighting.

Then we need to include a **DATABASE_URL** environment variable inside our .env file.

`DATABASE_URL="postgresql://postgres:<Your_PGADMIN4_password>@localhost:5432/<The_name_of_your_database>?schema=public"`

Once we have our _*DATABASE_URL*_ in our .env, and have PGADMIN4 ready we can run this line of code `npx prisma generate`. This wil generate a postgresql database within PGADMIN4.

Next we will run `npx prisma migrate dev`. This will create a _migration.sql_ file. Once created we should be able to test our backend api with the following routes to start.

`http://localhost:5001/api/register`

`http://localhost:5001/api/auth`

`http://localhost:5001/api/whoami`
