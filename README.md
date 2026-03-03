# Amber Prices for Home Assistant <!-- omit in toc -->

This integration is a replacement for the [Amber Electric](https://www.home-assistant.io/integrations/amberelectric) integration in Home Assistant.
It reuses much of the code of the Amber Electric integration.
It extends the functionality with:

- timely updates
- prices for the previous 6 hours
- advanced prices in forecasts (predicted, low, high)
- tarrif details (period and season) in current prices

These extensions allow the [Amber Prices Card](https://github.com/homotics/amber-prices-card) to display a full range of data,
and allow automations to use the extra data to make better decisions.
For more documentation on these extensions see the [Amber API](https://app.amber.com.au/developers/) documentation.

### Timely Updates

The prices for Amber update just after each 5 minute. They are initially an estimated price, but update shortly after to an actual price.
This integration checks every 5 seconds from the start of the 5 minute interval for the prices to be updated.
Once the actual price is received it waits until the next 5 minutes before it looks for more prices.
This allows automations to obtain the price data in a timely manner, rather than waiting up to 2 minutes to see the actual prices.

### Previous Prices

Previous prices can be useful to understand what happened recently with prices.
They may also be useful in predicting whether the forecast prices will materialise.

### Advanced Prices

Amber has created an advanced forecast system, that represents their predictions on the upcoming prices. It is a range that indicates where Amber thinks the price will be.
Smart Shift appears to use these prices.

### Tarrif Details

This indicates which time of use tarrif is currently active.

## Installation

### API Key

Follow the instructions for the [Amber Electric](https://www.home-assistant.io/integrations/amberelectric#getting-an-api-key) integration to obtain an API Key. If you already have an API Key for the Amber Electric integration you can reuse it.

### Install via HACS

[![Open your Home Assistant instance and open a repository inside the Home Assistant Community Store.](https://my.home-assistant.io/badges/hacs_repository.svg)](https://my.home-assistant.io/redirect/hacs_repository/?owner=homotics&repository=amber_prices&category=integration)

## How the integration works

In addition to the sensors described for the [Amber Electric](https://www.home-assistant.io/integrations/amberelectric#how-the-integration-works) integration, 
for each channel type there is an additional sensor:

- **Previous** - The prices for that channel for the previous 6 hours.

See the the [Amber Electric](https://www.home-assistant.io/integrations/amberelectric) integration for more details.
