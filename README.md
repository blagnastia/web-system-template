# Web system
- [x] Replace "WEB system" with your system name.
GettingDrunk

https://www.thecocktaildb.com/api.php

## Description
- [ ] Provide WEB system description in few sentences - its purpose, users, etc.

Web system in which users can input different ingridients and get a result on what coctails they could make, 

## Entity definition
- [X] Define the entity ("object" that will be manipulated) of WEB system

Cocktail (id(number 10), name (string 30), image, instruction (string 1000), dateModified string[yyyy-mm-ddThh:mm:ss], ingredients ???)

- [x] Entity should have a name
- [x] Entity should have 3 mandatory attributes:
    - [ ] ID - depending on specific service this could be a number or string
    - [ ] Creation date - (if applicable for specific service) ISO 8601 format date string ?????
    - [ ] Modification date - (if applicable for specific service) ISO 8601 format date string
- [ ] Entity should have at least 5 custom attributes
    - [ ] Each attribute should have a type defined: number, string, ISO 8601 date string, boolean, object, array or other
    - [ ] Each attribute should have restrictions defined: list of constants, or number range, or string length, or string format, or object schema, or array schema or other. For example, you can use `joi` language to define restrictions: https://github.com/hapijs/joi/blob/v13.1.2/API.md

## API definition
- [ ] Define specific service (konkrečios paslaugos) API methods that WEB system is going to use
- [ ] Optionally define additional API methods that WEB system is going to expose. sukurt savo?  
- [ ] API should have at least 4 methods
    - [x] A method to return entity by ID. Should not have request body
    - [x] A method to return multiple entities (Array) by ID. This method should support at least one header value to:
        - [ ] Return only entities that match pattern in one of its attributes
        - [ ] Return 10 entities starting provided index
        - [ ] Return sorted entities by one of its attributes (both ascending and descending)
        - [ ] Other (should be approved by Product Owner (PO))
    - [] A method to remove entity by ID. Returns removed entity. Should not have request body. favorite?
    - [ ] A method to update entity by ID. Accepts entity to update and returns updated entity. favorite list ?
- [ ] Each method should have HTTP method defined
- [ ] Each method should have URI defined (use {id} as entity ID placeholder)
- [ ] Should return all 4xx errors in unified format. Define format using `joi` language
- [ ] Should return all 5xx errors in unified format. Define format using `joi` language

GET /coctail/ingredients
401 Unauthorized

GET /coctail/ingredients?ingredient=Gin
nėra errorų, nes pasirenka tai, ką gali

PUT /coctail/search 
400 err message when validation fails

PUT coctail/inglist/:id
401 Unauthorized
400 err message when validation fails

DELETE coctail/inglist/:id
401 Unauthorized


## UI definition
- [ ] Define the structure of how visually the WEB system is going to look like
- [ ] Should have at least one view defined with https://wireframe.cc (or other wireframe tool):
- [x] The view should have a title
- [ ] The view should have a description of a service provided by web system
- [ ] The view should include at least 2 UI components:
    - [x] A component to display multiple entities with all their attribute values visible. It should be posible to remove and edit selected entity.
        - [ ] Depending on chosen header of API method that returns multiple entities, it should be posible to select specific 10 entities starting index, sort entities by attribute, filter entities by attribute pattern, or other (should be approved by Product Owner (PO))
    - [x] A component to create a new entity/edit existing entity. It should be posbile to create new entity and edit selected entity. ar realu sukurti savo nauja objekta? redaguoti jau sukurta objekta? 
        - [ ] Each attribute should have a dedicated editor field: text box for string or number, checkbox or radio buttons for boolean, date picker for date, etc. 
