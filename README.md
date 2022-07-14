# Main features of the app
- [] Reading data from storage
- [] Processing data for display
    - [] Switch timeframes
    - [] Add main averages and indicators
- [] Display data
    - [] Show several graphs? (2, 4..)
    - [] Allow easy selection of pairs
    - [] Display pool data (pair, liquidity, fee, address (link to Etherscan), link to Uniswap)
    - [] Display carrousel with latest prices from most popular crypto pairs
    - [] Pool list with most liquid pools and link to their graph


# Initial TODO list
- [X] Check best chart provider &rarr; Apexcharts. Other providers: canvasjs and lightweight charts from TradingView &rarr; It seems not possible
- [X] Check if json object can include methods
- [X] Create data downloader
- [X] Create object data methods
- [X] Upload initial seed app to heroku and run
    - [X] Create an express app, and inside it create the react app, in the client/ folder. See an example [here](https://daveceddia.com/deploy-react-express-app-heroku/)
    - [X] In the client/package.json file add 
    ```
            "proxy": "http://localhost:5000",
            "homepage": "https://uniswapv3-charts.herokuapp.com/",
    ```
    - [X] Text for the Procfile ```web: node index.js```
    - [X] In the main package.json file add 
    ```
            "heroku-postbuild": "cd client && npm install && npm run build"
    ```
    - [X] IMPORTANT. From this [page](https://create-react-app.dev/docs/deployment/ "Deployment on React app docs") Add the following lines/functions to the index.js server file:
    ```
            var path = require('path');

            app.use(express.static(path.join(__dirname, 'client/build')));

            app.get('*', function (req, res) {
            res.sendFile(path.join(__dirname, 'client/build', 'index.html'));
            });
    ```
- [] Clean code in PriceChart.js
    - [X] Make data be propagated
    - [X] Allow addition/deletion of averages
    - [] Study and use chart options
    - [] Make this component a function of symbol, timeframe...
- [] Create app structure (redux, components, etc)
- [] Clean up boilerplate code on index.html
- [] Prepare power point with logo, layout, etc...
- [] Figure out how to update data as it is created

## Features to add
- [] View liquidity history (this would have to be implemented in the reader as well)
- [] Have 1 hour observations data (this would have to be implemented in the reader)
- [] Download all the historical data (to be implemented in the reader)
- [] Add the possibility of viewing your balance of each coin
- [] How to update prices real time?
- [] How to update symbol list?
- [] Add token logos
- [] Use localStorage to save user settings
