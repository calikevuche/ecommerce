# Ecommerce 
A Microservice-based, E-commerce webapp.

Please read the following [EcommerceDesign Doc](EcommerceDesign.pdf) before proceeding...

## Dependencies ##
Use pip to install some of these dependencies
1. Python3
2. Requests
2. Flask
3. Sqlite3
4. NGINX webserver
5. POSTMAN

## How to launch Miroservice-based, Ecommerce ##
1. Set up the central database by running ecommerce.py
2. Copy over nginx.conf to local ngnix at \nginx-x.x.x\nginx-x.x.x\conf
3. Run NGINX as a background process
4. Run AccountService.py
5. Run ProudctService.py
6. Run CartService.py
7. Run OrderService.py
8. Run PaymentService.py

## Using the ecommerce app, from browsing to checkout ##
1. Launch POSTMAN. **Note: Responses are in JSON format, so it can be easily integrated with a front-end.**
2. Sequence of events to following for the demo:

    /ecommerce/v1/account/register : form-data: email, password, ... look at API Documentation <- register new account
    
    /ecommerce/v1/account/login :  form-data: email, password <-login to account
    
    /ecommerce/v1/product/ : form-data: name, price, description, category [1..4], image (File), stock <- **add new products**
    
    /ecommerce/v1/product/query : form-data: query (for api purposes)
    
    /ecommerce/v1/cart/product : form-data: username, password, productId <- add products to cart--do this with as many products
    
    /ecommerce/v1/cart/user : form-data: username, password <- see items in cart **view the shopping cart of the current user**
    
    /ecommerce/v1/payment/: form-data: username, password <- payment and checkout process; removes all products from cart and into orders
    
    /ecommerce/v1/cart/product/remove <- form-post: raw: {"productId":"x", "userId":"x"} <-remove one item from the cart
    
    /ecommerce/v1/order: <- **view the purchase history of the current user**
    
    /ecommerce/v1/account/logout: none <- logout of account
    
## POSTMAN API Documenation ##
[Ecommerce](https://documenter.getpostman.com/view/5404767/RWgwSGUM)

