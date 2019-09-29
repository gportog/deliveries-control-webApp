# deliveries-control-webApp
Web app to register and consult amount of products delivered by day, month or year.


## Back-end

**POST /login :** Redirects to our login provider.

**POST /logout :** Kills the user session.

**All the following routes fall under /api/v[version_number]**

**POST /deliveries :** Uploads a new delivery to the system.

**PUT /deliveries/:_id/ :** Uploads a new version of a delivery to the system.

**GET /deliveries?date_from=:date_from&date_to=:date_to&page_id=:page_id** Retrieves all deliveries registered in the system of a deliveryman logged in the system by a period of time.

**GET /deliveries/:_id :** Retrieves a delivery registered in the system by its id.


## Front-end

### Components

- **home :** Welcome message, icons to redirect to the search and create routes.
- **create-delivery :** Form to register a new delivery to the system. It uses the deliveries service `create` method.
- **edit-delivery :** Form to edit a delivery to the system. The `date` field is going to be disabled. It uses the deliveries service `getById` and `edit` method.
- **search-bar :** Form to search the deliveries by date.
- **search-results :** Table of all search results. It uses the deliveries service `search` method. On double click in a row, it redirects to the `/edit/:_id` route.

### Routes

- **/ :** If the user don't have a session in the app it redirects to the back-end `POST /login` route, otherwise it displays the **home** component.
- **/create :** Displays the **create-delivery** component.
- **/edit/:_id :** Displays the **edit-delivery** component.
- **/search :** Displays the **search-bar** and **search-results** components.

### Service

- **deliveries:**
    - **create(deliveryObj) :** Makes a call to the back-end route `POST /deliveries`.
    - **getById(_id) :** Makes a call to the back-end route `GET /deliveries/:_id`.
    - **edit(deliveryObj) :** Makes a call to the back-end route `PUT /deliveries/:_id/`.
    - **search(date_from, date_to, page_id) :** Makes a call to the back-end route `GET /deliveries?date_from=:date_from&date_to=:date_to&page_id=:page_id`

### Prototype

#### Home
![Home](/resources/home.png)

#### Create/Edit
![CreateEdit](/resources/create_edit.png)

#### Search
![Search](/resources/search.png)


## Getting started

```
- cp env-example .env
- open .env file and fill in the required environment variables
- npm install
- npm start
- open a new terminal window and run: npm install; npm start
- open a browser in the http://localhost:4200
```


## Contact
Name                 | Email                              | Role  
---------------------|------------------------------------|-----------|
Gustavo Porto Guedes | gustavo.guedes@fatec.sp.gov.br     | Developer 