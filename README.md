# Vinted (back end)

Welcome to the back-end repository of my vinted copy!

## User

### /user/signup (POST)

Create user account.

| Body       | Info     | Description          |
| ---------- | -------- | -------------------- |
| `email`    | Unique   | User's email address |
| `password` |          | User's password      |
| `username` | Required | User's username      |
| `phone`    |          | User's phone number  |

### /user/login (POST)

Log into user's account.

| Body       | Description          |
| ---------- | -------------------- |
| `email`    | User's email address |
| `password` | User's password      |

## Offer

### /offer/publish (POST)

Enable authenticated user to publish a new offer.

#### Headers

| Header  | Description  |
| ------- | ------------ |
| `token` | User's token |

#### FormData

| formData     | Description                      |
| ------------ | -------------------------------- |
| `title`      | Offer's title                    |
| `descrition` | Quick description of the product |
| `price`      | Product price                    |
| `condition`  | Product condition                |
| `city`       | Product location                 |
| `brand`      | Product brand                    |
| `size`       | Product size                     |
| `color`      | Product color                    |

### /offers/ (GET)

Get a list of offers that can be filtered by queries.

| Query      | Description                                                    |
| ---------- | -------------------------------------------------------------- |
| `title`    | Get a list of offers containing `title`                        |
| `priceMin` | Get offers that are more expensive than `priceMin`             |
| `priceMax` | Get offers that are cheaper than `priceMax`                    |
| `sort`     | `price-asc`: get a list of offers sorted by ascending prices   |
|            | `price-desc`: get a list of offers sorted by descending prices |
| `page`     | Manage pagination                                              |
| `limit`    | Set the maximum number of results per page                     |

### /offer/:id (GET)

Get a specific offer.

| Param | Required | Description         |
| ----- | -------- | ------------------- |
| `id`  | Yes      | Offer's database id |

### /payment (POST)

Pay for a product.

| Body          | Description                                            |
| ------------- | ------------------------------------------------------ |
| `stripeToken` | Token provided by Stripe to authentify the transaction |
| `title`       | Offer's title                                          |
| `price`       | Sum of the product's price and corresponding fees      |

## Packages & dependencies

- [Cloudinary](https://www.npmjs.com/package/cloudinary)
- [Cors](https://www.npmjs.com/package/cors)
- [crypto-js](https://www.npmjs.com/package/crypto-js)
- [Dotenv](https://www.npmjs.com/package/dotenv)
- [Express](https://www.npmjs.com/package/express)
- [Express-formidable](https://www.npmjs.com/package/express-formidable)
- [Mongoose](https://www.npmjs.com/package/mongoose)
- [stripe-js](https://www.npmjs.com/package/@stripe/stripe-js) (@stripe/stripe-js)
- [uid2](https://www.npmjs.com/package/uid2)

## Check this out!

- **[My Vinted copy](https://vinted-copy-arthur.netlify.app)**
- **The corresponding [front-end repository](https://github.com/ArthurHtbk/vinted-front)**
