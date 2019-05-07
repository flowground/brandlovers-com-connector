# ![LOGO](logo.png) BrandLovers Marketplace API V1 **flow**ground Connector

## Description

A generated **flow**ground connector for the BrandLovers Marketplace API V1 API (version 1.0.0).

Generated from: https://api.apis.guru/v2/specs/brandlovers.com/1.0.0/swagger.json<br/>
Generated at: 2019-05-07T17:39:49+03:00

## API Description

Allows sellers to: 1) Load products definitions to the BrandLovers marktplace. 2) Receive and update orders status. 3) Receive and update shipping information. 4) Receive and update customer tickets. All requests consume and return application/json content. All request must be authenticated and use HTTPS.

## Authorization

Supported authorization schemes:
- API Key
## Actions

### Returns all details of a order

> Returns all details of a single order, including last status, items shipped or not.

*Tags:* `order`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.
* `orderId` - _required_ - Unique Id of this order.

### Confirm shipment canceletion (when requested by the customer) or failure to deliver

> Confirm shipment canceletion (when requested by the customer) or failure to deliver one shipment

*Tags:* `order`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.
* `orderId` - _required_ - Unique Order Id

### Confirms that a shipment was delivered

> Confirms that a shipment was delivered. Must inform quantity of successfully deliverd items even if items deliverd was less than the original order

*Tags:* `order`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.
* `orderId` - _required_ - Unique Order Id

### Confirm item exchange

> This enpoint to confirm item exchange when failure to deliver or requested by the customer. All customer requests are tracket via trouble tickets

*Tags:* `order`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.
* `orderId` - _required_ - Unique Order Id

### Confirm order item return and refund

> Use this endpoint to return and refund items froma a order. In order to fully return an order list all items and applicate quantity.

*Tags:* `order`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.
* `orderId` - _required_ - Order unique Id

### Update new order to include shipment information

> Updates order to include shipment shiped information. This endpoint can be used to include a single or multiple shipments for any give order. In order to inform that all items of a order where shipped list all of them, including applicable quantities in the payload.

*Tags:* `order`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.
* `orderId` - _required_ - Unique Order Id

### Returns orders details

> Retuns a list of orders associated with this seller. The list is ordered by dateCreated.

*Tags:* `orders`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.
* `offset` - _optional_ - Number or items to skip when executing query. List starts at zero. If omitted will default to zero. Use this conjuction with `limit` to paginate across the results.
* `limit` - _optional_ - Number or items to return when executing query. Defaults to 10. Use this conjuction with `offset` to paginate across the results.

### Returns list of shipments

> Returns list of shipments. By default this will return list of the last shipments ordered by dateCreated, folowed by last update date.

*Tags:* `orders`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.
* `status` - _optional_ - Query by shippment status.
* `offset` - _optional_ - Number or items to skip when executing query. List starts at zero. If omitted will default to zero. Use this conjuction with `limit` to paginate across the results.
* `limit` - _optional_ - Number or items to return when executing query. Defaults to 10. Use this conjuction with `offset` to paginate across the results.

### Bulk update of order shipments

> Bulk update of order shipments status. This alows to inform multiple shipments status

*Tags:* `orders`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.

### Returns a list of shipments shipped

> Returns a list of shipments shipped. By Default returns items ordered by dateCreated folowed by last update

*Tags:* `orders`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.
* `status` - _optional_ - Product status.
    Possible values: NEW, APPROVED, DECLINED, PENDING.
* `offset` - _optional_ - Number or items to skip when executing query. List starts at zero. If omitted will default to zero. Use this conjuction with `limit` to paginate across the results.
* `limit` - _optional_ - Number or items to return when executing query. Defaults to 10. Use this conjuction with `offset` to paginate across the results.

### Bulk update of order shipments

> Allows bulk updates of orders shippments.

*Tags:* `orders`

### Return list of approved orders

> Returns a list of approved orders. Orders in the `approved` state must be fullfiled imediadetelly.

*Tags:* `orders`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.
* `offset` - _optional_ - Number or items to skip when executing query. List starts at zero. If omitted will default to zero. Use this conjuction with `limit` to paginate across the results.
* `limit` - _optional_ - Number or items to return when executing query. Defaults to 100, max 200. Use this in conjuction with `offset` to paginate across the results.

### Returns lists of canceled orders

> Returns a list with canceled orders. Canceled orders should not be fullfiled.

*Tags:* `orders`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.
* `offset` - _optional_ - Number or items to skip when executing query. List starts at zero. If omitted will default to zero. Use this conjuction with `limit` to paginate across the results.
* `limit` - _optional_ - Number or items to return when executing query. Default 100, max 250. Use this conjuction with `offset` to paginate across the results.

### Returns a list of orders successfully delivered associated with this seller.

*Tags:* `orders`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.
* `offset` - _optional_ - Number or items to skip when executing query. List starts at zero. If omitted will default to zero. Use this conjuction with `limit` to paginate across the results.
* `limit` - _optional_ - Number or items to return when executing query. Defaults to 10. Use this conjuction with `offset` to paginate across the results.

### Returns a list of orders flagged as new.

> Returns a list of orders flagged as new. New orders should not be fullfiled until marketplace flags them as approved.

*Tags:* `orders`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.
* `offset` - _optional_ - Number or items to skip when executing query. List starts at zero. If omitted will default to zero. Use this conjuction with `limit` to paginate across the results.
* `limit` - _optional_ - Number or items to return when executing query. Defaults to 100. Max 250. Use this conjuction with `offset` to paginate across the results.

### Returns a list of partially deliverd orders

> Returns a list of partially deliverd orders. This is a list of orders with items shipped but with not all items ackwlodged as deliverd

*Tags:* `orders`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.
* `offset` - _optional_ - Number or items to skip when executing query. List starts at zero. If omitted will default to zero. Use this conjuction with `limit` to paginate across the results.
* `limit` - _optional_ - Number or items to return when executing query. Defaults to 100. Max 250. Use this conjuction with `offset` to paginate across the results.

### Returns a list of orders partially fullfiled

> Returns a list of orders that contain one (or more) items that where not shipped. This will list the entire order as well the items with peding shipment. Use this service to track orders that need to be fullfiled.

*Tags:* `orders`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.
* `offset` - _optional_ - Number or items to skip when executing query. List starts at zero. If omitted will default to zero. Use this conjuction with `limit` to paginate across the results.
* `limit` - _optional_ - Number or items to return when executing query. Defaults to 100. Use this conjuction with `offset` to paginate across the results.

### Returns a list with orders fully sent

> Returns a list with orders completely fullfiled, this means orders with all items sent. Orders will ordered by dateCreated fowllowed by last update

*Tags:* `orders`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.
* `offset` - _optional_ - Number or items to skip when executing query. List starts at zero. If omitted will default to zero. Use this conjuction with `limit` to paginate across the results.
* `limit` - _optional_ - Number or items to return when executing query. Defaults to 10. Use this conjuction with `offset` to paginate across the results.

### Create a new product to the marketplace

> Use this enpoint to create a single new product to the Marketplace. This enpoint expects a json document with one product. If you whant to upload multiple products in a single API call use POST /products method. The server will load each product as an individual item that can be manipulated using your own `skuSellerId`. This system is idenpontent, this means that once a `skuSellerId` is created it cannot be re-created using this tool. In order to update, edit a product use the PUT method with the correct reference to your `skuSellerId`

*Tags:* `product`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.

### Returns details of a single product using the seller `skuSellerId`

> Returns detailed information of a single product with the seller `skuSellerId`. This service will return a json document with product detail, status, price, invetory among other infomarion availble in the Brand Lovers marketplace

*Tags:* `product`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.
* `skuSellerId` - _required_ - SKU ID do Lojista.

### Update product details

> Update a single product information such as name, brand, attribute, dimension, etc. Please note that data from your request will be merged with existing data. This allows you to easliy update only certain fields without the need to re-inform the other unchanged fields. For example in order to update just the field `title` simply send just this field with new information, remaining fields will not be changed. In order to erase an item the field must be informed as its default value, for example in order to erase the `videos` field must be sent as videos:[]. The `skuSellerId` field is always mandatory in the path and in the product json Object.

*Tags:* `products`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.
* `skuSellerId` - _required_ - Unique Product Id (SKU) in the seller system that will be updated.

### Allows seller to update prices of a single SKU

> Allows seller to set the SKU prices (MSRP and/or offer price). All prices must be informed in cents. No commas or periods are accepeted. For example one dollar should be informed as 100. Same as $1,2345.67 must be informed solely as 1234567

*Tags:* `product`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.
* `skuSellerId` - _required_ - Product SKU

### Enable/disable a single product in the Marketplace

> Update product status in the Marketplace. Set to `true` to enable, `false` to disable sale.

*Tags:* `product`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.
* `skuSellerId` - _required_ - Unique Product Id (SKU) in the seller system

### Update a single product stock

> Update a single product inventory information. Products with zero stock will not be eligible for sale.

*Tags:* `product`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.
* `skuSellerId` - _required_ - Unique Product Id (SKU) in the seller system that will be updated

### Returns a list of products loaded into BrandLovers Marketplace

> Get a list of my products loaded into the Marketplace. This dosen't means that products are eligible for sale, just that they are loaded in the database.

*Tags:* `products`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.
* `offset` - _optional_ - Number or items to skip when executing query. List starts at zero. If omitted will default to zero. Use this conjuction with `limit` to paginate across the results.
* `limit` - _optional_ - Number of items to retun. Defaults to 100. Max alowed is 200. Use this conjuction with `offset` to paginate across the results.

### Allows new products from the seller to be loaded into the marketplace

> This enpoint to creates new products in the Marketplace using `skuSellerId` as a primary key. This enpoint expects a json document with array of products. The server will load each product as an individual item that can be manipulated using your own `skuSellerId`. All requests to This endpoint are idenpontent with respect of the `skuSellerId`, this means that once a `skuSellerId` is created it cannot be re-created using this tool. In order to update use the PUT method with the correct `skuSellerId`. You can also use the POST /product to create a single product per request

*Tags:* `products`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.

### Allows bulk update of product prices.

> Allows bulk update of product prices. This endpoint expects a json document with an array of products with the `skuSellerId` and the new price. Server will process each new product update individually and will ackwlodge as much updates as possible, even if a single product update fails. After this request you can query product final status with GET /product/status

*Tags:* `products`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.

### Returns seller products status in the marketplace

> Returns a list with seller products status. Please note that this endpoint will not return all details of each product, just the skuSellerId and status. Also please note that this endpoint will return 250 products per call. For full details of a given procuct use GET /product/{skuSellerId}

*Tags:* `products`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.
* `offset` - _optional_ - Number or items to skip when executing query. List starts at zero. If omitted will default to zero. Use this conjuction with `limit` to paginate across the results.
* `limit` - _optional_ - Number of items to return in this query. Defaults to 250. Maximum 1000. Use this conjuction with `offset` to paginate across the results.

### Bulk enable/disable products in the marketplace

> Bulk enable/disable products in the marketplace. This endpoint requires an array of objects with the seller SKU `skuSellerId` and boolean value that defines if the product is enabled or not for sale. This endpoint can be used to set a single product or many products.

*Tags:* `products`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.

### Returns products that are successfully listed for sale.

*Tags:* `products`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.
* `offset` - _optional_ - Number or items to skip when executing query. List starts at zero. If omitted will default to zero. Use this conjuction with `limit` to paginate across the results.
* `limit` - _optional_ - Number or items to return when executing query. Defaults to 10. Use this conjuction with `offset` to paginate across the results.

### Bulk product stock update

> Bulk product stock update. This endpoint expect a array of products `skuSellerId` with new inventory data

*Tags:* `products`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.

### Creates a new trouble ticket

> Use this service to create a new trouble ticket. Use this to include relevant information about the order, comunicate with the customer or marketplace team. Whenever possible message will be pushed to Mobile first. This is the primary mean of comunicaiton with the customer regarding orders, shippments, shippments status. New tickets will be automatically be set to 'OPEN'. Trouble tickets need to be associated with a orderId or customer. New tickets can optionally include a new message.

*Tags:* `tickets`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.

### Add new message to trouble ticket

> Add a new message to this trouble ticket. Messages can be `CUSTOMER` (customer will be able to see it) or `INTERNAL`.

*Tags:* `tickets`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.
* `ticketId` - _required_ - Trouble ticket ID.

### Get trouble ticket messages

> Returns trouble ticket history with all messages exchanged. Only tickets related to your seller will be returned. Attempt to read other tickets will return 403 (acess denied).

*Tags:* `tickets`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.
* `ticketId` - _required_ - Trouble ticket ID.
* `offset` - _optional_ - Number or items to skip when executing query. List starts at zero. If omitted will default to zero. Use this conjuction with `limit` to paginate across the results.
* `limit` - _optional_ - Number or items to return when executing query. Defaults to 10. Use this conjuction with `offset` to paginate across the results.

### Update trouble ticket status

> Alows the seller to update the status of a trouble ticket

*Tags:* `tickets`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.
* `ticketId` - _required_ - Trouble ticket unique identification

### Get customers trouble tickets

> Allows seller to receive and status, queries, requests and complaints from customers. As well related messages

*Tags:* `tickets`

#### Input Parameters
* `authorization` - _required_ - Authorization token. The Authorization token can be found in your Admin console.
* `status` - _optional_ - Query by trouble ticket status
    Possible values: OPEN, REOPENED, CLOSED.
* `offset` - _optional_ - Number or items to skip when executing query. List starts at zero. If omitted will default to zero. Use this conjuction with `limit` to paginate across the results.
* `limit` - _optional_ - Number or items to return when executing query. Defaults to 10. Use this conjuction with `offset` to paginate across the results.

## License

**flow**ground :- Telekom iPaaS / brandlovers-com-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
