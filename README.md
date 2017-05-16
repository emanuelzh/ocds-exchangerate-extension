#Exchange Rate Extension

Use case 

We have encountered a range of situations where publishers or data users may wish to provide/access multiple currency values. These include where:
Two currencies are reported for a given contract. For example, a document might give values in both USD and another currency.
A contract agrees a fixed exchange rate for payments. For example, a contract is agreed in USD, but with a fixed exchange rate to convert this into MXN when payments are made. Sometimes the second value is declared. Sometimes only the rate is declared (as this will be the rate used).
Values in the dataset are in multiple currencies, but users want to access the values in a single currency. For example, an application may want to sum up total contract values in USD, even if original contracts were in a range of other values.


Fields & Definitions

This extension for “value” provides optional properties for altAmount, altCurrency, exchangeRate, and exchangeRateDate.
amount should be the value in the first Currency 
altAmount should be the value in a secondary currency specified in altCurrency.
exchangeRate is the exchange rate if specified.
exchangeRateDate is the date on which the exchange rate applied. 


Example JSON: 

```
"value": {
   "amount": 6563700,
   "currency":"MXN",
   "altAmount":429000,
   "altCurrency":"USD",
   "exchangeRate":0.065,
   "exchangeRateDate":"2015-11-04T00:00:00-05:00"
}
```

When should these fields be used

When the extension is used, altCurrency must always be provided, and either altAmount or exchangeRate must be provided.
