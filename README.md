# E-comm-HTTP-requests-using-OOP
Use object oriented to call the right http request depending on what type of E-com store the user is connected to (Shopify, Lightspeed, etc.).

## Challenge
The app needs to perform the same actions for e-comm websites depending on which type of E-comm the user is using. For exemple, a user must be able to view his products whether his shop is with Shopify or Lightspeed. Considering the user can be connected to multiple shops, all from different e-comm sources, how can the user's action call the right HTTP request to the right API?

![image](https://user-images.githubusercontent.com/36003383/183108114-188534fa-6e80-4516-b8ff-938ef6f84b93.png)

The easy and wrong way to do it is to create an endpoint for each request: GetProductsShopify, GetProductsLightspeed. This doesn't follow clean code principles and doesn't reduce code duplication. We want our code to dynmically decide which type of request is suited for our user.

## Strategy
1. Let's use Oriented Object Programming to filter the request types

- Create abstract ShopAPI class
- Create child classes that derive from ShopAPI: ShopifyAPI, LightspeedAPI, etc.
- Add fields and methods. Make sure the childs override the methods with the right HTTP request.
- Spread your routes to make it cleaner later in the server. `/shopifyAPI/getProducts` and `/lightspeedAPI/getProducts`

![image](https://user-images.githubusercontent.com/36003383/183122928-06cc8717-97f5-4a73-8381-5c3800f03c14.png)

