 ### Axios
 
 Goal: Integrate a third party API using axios.
 
 Required Reading:
 
  - [Axios Tutorial](https://medium.com/@amchris98/axios-tutorial-7e1fe28b8b05)
  - [HTTP Module in NestJS](https://docs.nestjs.com/techniques/http-module)
  
Online Shop: 

 > Create a new REST API that handles the creation of orders. The following constraints apply:
 >
 > - You get a single JSON object as input. This object will contain the order timestamp, the delivery address and a list of products (product ID and quantity) contained in the order.
 > - You return an Order entity if the operation was successful. If not, you return an exception response.
 > - The app has to select a strategy for finding from which locations should the products be taken. The strategy should be selected based on an environment variable. The following strategies should be created: 
 >   - **Most abundant** - take each product from the location which has the largest stock for that particular product.
 >   - **Closest location** -  find the location which is the closest to the order's delivery address, take all the available needed products from that location. Until we have all the products we need, repeat the before steps (by going to the second closest location, then to the third and so on). 
 > - The app then runs the strategy, obtaining a list of objects with the following structure: location, product, quantity (= how many items of the given product are taken from the given location). If the strategy is unable to find a suitable set of locations, it should throw an exception.
 > - The stocks are be updated by subtracting the shipped goods. 
 > - Afterwards the order is persisted in the database and returned.
 > 
 > You will need to also create the underlying mongoose models and corresponding repository objects for the stocks, locations, orders, etc.
 >
 > To compute the distances for the *closest location* strategy, use axios to call the [MapQuest route matrix API](https://developer.mapquest.com/documentation/directions-api/route-matrix/post/). You will first need to [register on the MapQuest site](https://developer.mapquest.com/plan_purchase/steps/business_edition/business_edition_free/register) and obtain an API Key.
 
 Further Resources:
 
  - [Axios documentation](https://github.com/axios/axios)