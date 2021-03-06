# WEB system
- Dad Jokes powered by VGTU
- [ ] Replace "WEB system" with your system name

## Description
- Dad Jokes powered by VGTU is a system that displays you a random dad joke. You don't have to register or create any user, enter URL of this system into your browser and voilà, dad joke is presented to you! If you are not satisfied with current joke, you can generate a new one by clicking on a new joke button! Enjoy!

- [ ] Provide WEB system description in few sentences - its purpose, users, etc.

## Entity definition
- dadJoke(id(number(1000)), joke(string(10000)), dateCreated(date), likeCounter(number), lastTimeDownloaded(date), lastTimeLiked(date), timesDownloaded(number))

- [ ] Define the entity ("object" that will be manipulated) of WEB system
- [ ] Entity should have a name
- [ ] Entity should have 3 mandatory attributes:
    - [ ] ID - depending on specific service this could be a number or string
    - [ ] Creation date - (if applicable for specific service) ISO 8601 format date string
    - [ ] Modification date - (if applicable for specific service) ISO 8601 format date string
- [ ] Entity should have at least 5 custom attributes
    - [ ] Each attribute should have a type defined: number, string, ISO 8601 date string, boolean, object, array or other
    - [ ] Each attribute should have restrictions defined: list of constants, or number range, or string length, or string format, or object schema, or array schema or other. For example, you can use `joi` language to define restrictions: https://github.com/hapijs/joi/blob/v13.1.2/API.md

## API definition
- Fetch a random dad joke - GET https://icanhazdadjoke.com/ - ERROR 500: Couldn't retrieve joke, try again (server error);
- Create dad joke - POST /api/jokes - body will be joke (without ID (auto-generated)) - ERROR 400: Too much symbols; Illegal symbols; 
- Download dad joke - GET /api/jokes/:id - as TXT - ERROR 500: Couldn't create a joke in your system (server error);
- Search for dad jokes - GET https://icanhazdadjoke.com/search - ERROR 400: Couldn't find joke (joke/id not found); Too much symbols; Illegal symbols;
- Like a joke - POST /api/jokeS/:id/likeCounter - ERROR 500: Couldn't count like (server error);

- [ ] Define specific service (konkrečios paslaugos) API methods that WEB system is going to use
- [ ] Optionally define additional API methods that WEB system is going to expose
- [ ] API should have at least 4 methods
    - [ ] A method to return entity by ID. Should not have request body
    - [ ] A method to return multiple entities (Array) by ID. This method should support at least one header value to:
        - [ ] Return only entities that match pattern in one of its attributes
        - [ ] Return 10 entities starting provided index
        - [ ] Return sorted entities by one of its attributes (both ascending and descending)
        - [ ] Other (should be approved by Product Owner (PO))
    - [ ] A method to remove entity by ID. Returns removed entity. Should not have request body
    - [ ] A method to update entity by ID. Accepts entity to update and returns updated entity
- [ ] Each method should have HTTP method defined
- [ ] Each method should have URI defined (use {id} as entity ID placeholder)
- [ ] Should return all 4xx errors in unified format. Define format using `joi` language
- [ ] Should return all 5xx errors in unified format. Define format using `joi` language

## UI definition
- Simple site with an image (around image there are counters for: times liked, times downloaded, date created, last time liked and last time downloaded) displayed up front and text-box below with a joke displayed in it, below text-box there are 4 buttons (new joke, create joke , download joke, search for joke and like a joke)
- https://wireframe.cc/HLU00D

- [ ] Define the structure of how visually the WEB system is going to look like
- [ ] Should have at least one view defined with https://wireframe.cc (or other wireframe tool):
- [ ] The view should have a title
- [ ] The view should have a description of a service provided by web system
- [ ] The view should include at least 2 UI components:
    - [ ] A component to display multiple entities with all their attribute values visible. It should be posible to remove and edit selected entity.
        - [ ] Depending on chosen header of API method that returns multiple entities, it should be posible to select specific 10 entities starting index, sort entities by attribute, filter entities by attribute pattern, or other (should be approved by Product Owner (PO))
    - [ ] A component to create a new entity/edit existing entity. It should be posbile to create new entity and edit selected entity
        - [ ] Each attribute should have a dedicated editor field: text box for string or number, checkbox or radio buttons for boolean, date picker for date, etc.
