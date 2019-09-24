---
title: "Portfolio"
date: "2019-09-23"
author: "Faris Habib"
path: "/showcase"
---

# Applications

---

## Tesla Feedback Form

[![Tesla Feedback App](../images/tesla-feedback-sample.png?raw=true "Click to view app.")](https://teslafeedback.herokuapp.com/)

<i>A web form that collects customer feedback on their Tesla dealership experience and sends that data to a Postgres database. Additional features include emailing the user. </i>

#### Features include:

  - Data collection using Python and Flask

  - Emails user w/ feedback summary using Mailtrap

  - Validates information to check for duplicate submissions

  - Deployed with Heroku


## Cryptocurrency Price Tracker

[![Crypto App](../images/crypto-sample.png?raw=true "Price Info. Click to view app.")](https://damp-temple-98185.herokuapp.com/)

<i>A cryptocurrency app that charts Bitcoin's price over the last 3 months. Additional features include pricing information for the top 100 cryptocurrencies.</i>

#### Features include:

  - Retrieves, selects and organizes cryptocurrency pricing data using CoinCap API

  - View price, volume, market cap, supply, & change information on the top 100 cryptocurrencies in the market

  - Data rendered in React components, Chart.js graphs and Semantic UI tables

  - Heavy emphasis on visual aesthetics for client using Semantic UI, React, and Styled-Components

  - Deployed to Heroku for simple viewing


## Mtn Maps

[![Mtn Maps](../images/mtn-maps-sample.png?raw=true "Mtn Maps Trail Markers & Popup Info")]()

<i>Mtn Maps allows you to input an address and locate the nearest hiking trails in the area.
When the markers are rendered information about the closest trails can be seen with links to more info such as trip reports.</i>


#### Features include:

  - Web mapping interface w/ MapBox API & MERN stack for intuitive experience

  - Geocoder in the search bar, so trails can be located from any address inputted

  - Trail gain, elevation, rating, and trip reports

  - Deployed to EC2 on AWS for future scalability enhancements


## Twitch.tv

[![Twitch](../images/fec-sample.png?raw=true "Twitch Sample")]()

<i>An application that mirrors Twitch.tv, a popular video and streaming website.
Main emphasis is on overall design and rendering of main features including streamer videos, chat, carousel, and profile services</i>

#### Features include:

  - View streamer videos from collection of over 100 streams

  - Emphasis on overall design and layout with React & Styled-Components

  - Modular back end deployed with AWS for future scalability enhancements

  - Option to follow streamers


## ESPN

[![ESPN](../images/sdc-sample.png?raw=true "ESPN Sample")]()

<i>An application that mirrors ESPN NFL team page of the Los Angeles Rams, scaled to accept over 40 million game records.
Displays team standings with divisional W-L-T record, percentage, as well as the points scored and points given up. </i>


#### Features include:

  - Redesigned database in PostgreSQL and Cassandra to accept over 40 million records in under 15 minutes

  - Deployed service in Docker containers to AWS EC2 for horizontal scaling

  - Achieves 10,000 RPS with less than 2000ms latency after stress-testing with New Relic & Loader.io