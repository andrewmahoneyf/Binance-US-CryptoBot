# CryptoBot

## NodeJS trading bot for Binance

This is an experimental terminal bot for auto trading on binance.us exchange. If you're looking for a bot for binance.com please check out my other repo [here](https://github.com/andrewmahoneyf/CryptoBot).

## Configuration

1.  [Signup](https://www.binance.us/?ref=35002429) for Binance US
2.  Enable Two-factor Authentication
3.  Go to [API Management](https://www.binance.us/en/usercenter/settings/api-management), and create a new Api Key

        [✓] Read Info [✓] Enable Trading [] Enable Withdrawals

4.  Create a `.env` file and insert your API and Secret Keys

    `cp .env.tmpl .env`

        API_KEY=...

        API_SECRET=...

5.  If holding BNB, turn on using BNB for trade fees in your [account](https://www.binance.us/en/usercenter/dashboard/overview) to save 25%. Option to hold BNB along with the min balance can be set in the `constants.js` file. More about trade fees and tiers can be found [here](https://www.binance.us/en/fee/schedule).

6.  Optional: alter additional bot presets such as portfolio allocation or trade intervals in `constants.js`
7.  Make sure to turn off your computers energy saving settings so that your terminal process won't pause if your computer goes to sleep. Alternatively, you can prepend `caffeinate` to your start command.

---

## Dependencies

[us-binance-api-node](https://github.com/andrewmahoneyf/us-binance-api-node)

[chart_utils](https://github.com/vpfautz/chart_utils)

## Usage

    yarn start:dev - (starts the development server for testing. No real orders will be sent.)

    yarn start - (creates a build and runs the production server. Warning: orders are now live.)

## Run in a Docker container

[Install Docker](https://docs.docker.com/install/)

    # Build the image
    $ docker build -t bot-img .

    # Run the image
    $ docker run -d -ti --name crypto-bot bot-img

    # Print bots output logs
    $ docker logs crypto-bot

    # If you want to enter the container
    $ docker attach crypto-bot

    # If you want to stop the container
    $ docker stop crypto-bot

    # If you want to clean unused containers/images
    $ docker system prune

## DISCLAIMER

    Use this bot at your own risk. I am not responsible for any potential losses.
    There are no warranties or guarantees expressed or implied.
    You assume all responsibility and liability.

## Contributing

    Fork this Repo
    Commit and push your changes
    Create a new Pull Request

## Roadmap

- [x] Configure Binance API routes
- [x] Set main structure with balance, budget, and allocation functionality
- [x] Handle logic for buy and sell orders
- [x] Calculate MACD values
- [x] Calculate RSI values
- [x] Setup cron task
- [x] Add environment variables for dev and production
- [x] Handle BNB min holdings
- [x] Allow custom trade or stable pairs
- [x] Release V1
- [x] Set-up Docker
- [x] Clean-up log outputs with tables and ora spinners
- [ ] Integrate websockets and batch orders
- [ ] Add configurations for other technical indicators
- [ ] Release V2
- [ ] Get sentiment analysis from Twitter or StockTwits
- [ ] Integrate [coindar calendar](https://coindar.org) for upcoming news
- [ ] Develop algo for selecting top 5 altcoins
- [ ] Release V3

## Donate

BTC: 16n7SXp1rxtJ5u4kSAZ8aFa7n3mCaxEEfR

LTC: LakZsKAb4TzCM4sjLdGZkrpdWvCcATiQzk

ETH: 0x01010a9cbffe37d4e38817a4d446e5a2c1a102c1

---

## License

Code released under the [MIT License](https://opensource.org/licenses/MIT).

---
