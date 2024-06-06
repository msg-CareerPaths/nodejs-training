# 4. Database & Entities [6-8 hours]

**Goal:** 
- Creating the entities for your database
- Using TypeORM & PostgreSQL to persist the application data.
- Connecting locally to the database to validate the schema.

## Data Model
![Data Model](https://raw.githubusercontent.com/msg-CareerPaths/nodejs-training/main/diagrams/careerStart-data-model.svg "Data Model")

## Environment Setup
- Install [pgAdmin](https://www.pgadmin.org/download/) to be able to connect to your database locally.

## Mandatory Materials:

**Videos:**
- [NestJS with TypeORM](https://youtu.be/qvhqUMRuquw)
- [Connecting to your database locally](https://youtu.be/UjQiwonRMas)

**Reading:**

 - [TypeORM Documentation](https://typeorm.io)
 - [Integrating TypeORM with NestJS](https://docs.nestjs.com/techniques/database)
 - [Using PG with TypeORM](https://www.thisdot.co/blog/connecting-to-postgresql-using-typeorm)
 - [SQL Relationships](https://blog.devart.com/types-of-relationships-in-sql-server-database.html)
 - [TypeORM relationships](https://orkhan.gitbook.io/typeorm/docs/relations)


## Online Shop: 
 > 1. Run `npm install --save @nestjs/typeorm typeorm pg reflect-metadata`
 > 2. Integrate TypeORM with PostgreSQL, in your NestJS application. You will now store your data within the database. Add the `TypeOrmModule.forRoot` in your `app.module.ts` with `type: postgres` in the configuration. Start your application to test that it connects successfully.
 >
 > 3. Make sure your have set the `synchronize: true` in the `.forRoot()` configuration so the application will update your database schema.
 > 
 > 4. Create the entities in the `/domain` folder for each respective `feature` folder one-by-one. Use the `TypeOrmModule.forFeature([<your_entity_class>])` in each respective `feature` module.
 >
 > 5. For each entity create annotations for their respective relationships (using `@Entity`, `@OneToOne`, `@ManyToOne`, etc)
 > 
 > 6. Start your application and connect using `pgAdmin`. Check that your table schema is correct.
 >
 > 7. Create repositories for each of your entities in `/repository` folder. Name them `<your_entity_name>.repository.ts`. This should be a provider class using the `@Injectable` annotation. While this might seem redundant, since NestJS already offers a provider for the repository functionality, it's a useful abstraction for more complex queries in the future
 >
 
 **Note:** PostgreSQL has support to UUID, so you can use it instead of commonly used auto-increment integer. UUID is helpful to avoid a normal attack in which the hacker tries to increase or decrease an entity ID to discover new information.
 
In TypeORM this is done by setting a column with the following annotation:
 ```typescript
@PrimaryGeneratedColumn("uuid")
id: string;
 ```

### Folder Structure Example

```
./src
-----health.controller.ts
-----app.module.ts
-----/customers
------------customers.module.ts
------------/controller
------------/mapper
------------/service
------------/domain
-------------------customer.domain.ts
------------/dto
------------/repository
-----------------------customers.repository.ts
```

## Further Resources

- [Keeping your secrets safe using environment variables](https://docs.nestjs.com/techniques/configuration)
- [TypeORM: Migrations](https://typeorm.io/#/migrations)
- [NestJS: Migrations](https://docs.nestjs.com/techniques/database#migrations)