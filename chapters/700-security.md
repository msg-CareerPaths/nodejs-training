# 7. Security [1 days]

**Goal:** 
- Add user authentication and authorization to your backend.
- Test using Postman and your local OpenAPI UI.

## Mandatory Materials:
**Videos:**
- [Session vs Token Authentication](https://youtu.be/UBUNrFtufWo)
- [JWT](https://youtu.be/P2CPd9ynFLg)
- [NestJS Authentication](https://youtu.be/twaUdKr06kA)

**Reading:**
- [Take note of the Strategy Design Pattern](https://refactoring.guru/design-patterns/strategy)
- [Authentication](https://docs.nestjs.com/security/authentication)
- [Guards](https://docs.nestjs.com/guards#guards)
- [Security in OpenAPI](https://docs.nestjs.com/openapi/security)

## Online Shop:

> 1. Add authentication based on JWT tokens, accessible only for registered customers. You will create an admin role and a customer role, which will determine their permissions within the api.
> 
> 2. This should be added to a new feature module in an `auth` folder which will reference the `customers` feature.
>
> 2. Secure all your routes in such way that only admins can create, update and delete products, and only admin and customers can access the rest of the endpoints.
>
> 3. Test using Postman to understand how the actual HTTP request looks.
>
> 4. Add the OpenAPI configuration and test it using your OpenAPI UI.

### Folder Structure Example

```
./src
-----health.controller.ts
-----app.module.ts
-----/auth
----------auth.module.ts
----------/strategies
--------------------jwt-auth.strategy.ts
--------------------local-auth.strategy.ts
----------/guards
----------------jwt-auth.guard.ts
----------------local-auth.guard.ts
----------/services
-----------------auth.service.ts
----------/dto
-----------------auth.dto.ts
----------/controllers
----------------------auth.controller.ts
```

## Further Resources:
- [Helmet](https://docs.nestjs.com/security/helmet)
- [Developing a Secure API with NestJS: Getting Started](https://auth0.com/blog/developing-a-secure-api-with-nestjs-getting-started/)
