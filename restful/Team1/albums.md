# API albums' especifications


## Data params' description

  | Field name   |      Type      |  Description |
  |--------------|:--------------:|-------------:|
  |userId        |[integer]       |              |
  |id            |[integer]       |              |
  |title         |[alphanumeric]  |              |
 

**List Albums**
----
  Returns json data about all the albums.

* **URL**

  /albums

* **Method:**

  `GET`
  
* **URL Params**

  None 
  
* **Data Params**

  None

* **Success Response:**

  * **Code:** 201 <br />
    **Content:** 
  ```javascript
      [
        {
          "albumId": 1,
          "id": 1,
          "title": "accusamus beatae ad facilis cum similique qui sunt",
          "url": "http://placehold.it/600/92c952",
          "thumbnailUrl": "http://placehold.it/150/92c952"
        },
        {
          "albumId": 1,
          "id": 2,
          "title": "reprehenderit est deserunt velit ipsam",
          "url": "http://placehold.it/600/771796",
          "thumbnailUrl": "http://placehold.it/150/771796"
        },
        {
          "albumId": 1,
          "id": 3,
          "title": "officia porro iure quia iusto qui ipsa ut modi",
          "url": "http://placehold.it/600/24f355",
          "thumbnailUrl": "http://placehold.it/150/24f355"
        },
      ]
  ```
 
* **Error Response:**

  * **Code:** 404 NOT FOUND <br />
    **Content:** `{ error : "This photos don't exist" }`

* **Sample Call:**

  ```javascript
    $.ajax({
      url: "/photos/",
      dataType: "json",
      type : "GET",
      success : function(r) {
        console.log(r);
      }
    });
  ```
  
**Show Album**
----
  Returns json data about a single album.

* **URL**

  /album/:id

* **Method:**

  `GET`
  
*  **URL Params**

   **Required:**
   `userId=[integer]`
   `id=[integer]`

* **Data Params**

  None

* **Success Response:**

  * **Code:** 201 <br />
    **Content:** 
  ```javascript
      {
        "albumId": 1,
        "id": 1,
        "title": "accusamus beatae ad facilis cum similique qui sunt",
        "url": "http://placehold.it/600/92c952",
        "thumbnailUrl": "http://placehold.it/150/92c952"
      }
  ```
 
* **Error Response:**

  * **Code:** 404 NOT FOUND <br />
    **Content:** `{ error : "This photo doesn't exist" }`

* **Sample Call:**

  ```javascript
    $.ajax({
      url: "/photos/1",
      dataType: "json",
      type : "GET",
      success : function(r) {
        console.log(r);
      }
    });
  ```
**Create photo**
----
  Returns json data about a photo created.

* **URL**

  /photos

* **Method:**

  `POST`
  
*  **URL Params**
  
  None

* **Data Params**

  `albumId`
  `title` 
  `file`
    
  *Example:*
  ```  
  albumId: 1,
  title: "officia porro iure quia iusto qui ipsa ut modi", 
  file: "/home/user/image.jpg"
  ```
* **Success Response:**

  * **Code:** 201 <br />
    **Content:** 
    ```javascript
      {
        "albumId": 1,
        "id": 1,
        "title": "accusamus beatae ad facilis cum similique qui sunt",
        "url": "http://placehold.it/600/92c952",
        "thumbnailUrl": "http://placehold.it/150/92c952"
      }
    ```
 
* **Error Response:**

  * **Code:** 400 BAD REQUEST <br />
    **Content:** `{ error : "File's size not supported" }`

* **Sample Call:**

  ```javascript
    $.ajax({
      url: "/photos/",
      dataType: "json",
      data: {
        albumId: 1,
        title: "officia porro iure quia iusto qui ipsa ut modi",
        file: "/home/user/image.jpg"
      }
      type : "POST",
      success : function(r) {
        console.log(r);
      }
    });
  ```
  
**Edit photo**
----
  Returns json data about a photo's update.

* **URL**

  /photos

* **Method:**

  `PUT`
  
*  **URL Params**
  
  None

* **Data Params**

  `albumId`
  `title` 
  `file`
  
  *Example:*
  ```  
    albumId: 1,
    title: "officia porro iure quia iusto qui ipsa ut modi", 
    file: "/home/user/image.jpg"
  ```
* **Success Response:**

  * **Code:** 201 <br />
    **Content:**
  ```javascript
      {
        "albumId": 1,
        "id": 1,
        "title": "accusamus beatae ad facilis cum similique qui sunt",
        "url": "http://placehold.it/600/92c952",
        "thumbnailUrl": "http://placehold.it/150/92c952"
      }
  ```
 
* **Error Response:**

  * **Code:** 400 BAD REQUEST <br />
    **Content:** `{ error : "File's size not supported" }`

* **Sample Call:**

  ```javascript
    $.ajax({
      url: "/photos",
      dataType: "json",
      data: {
        albumId: 1,
        title: "officia porro iure quia iusto qui ipsa ut modi",
        file: "/home/user/image.jpg"
      }
      type : "PUT",
      success : function(r) {
        console.log(r);
      }
    });
  ```

**Delete photo**
----
  Returns json data about a deleted photo.

* **URL**

  /photos

* **Method:**

  `DELETE`
  
*  **URL Params**

  id=[integer]

* **Data Params**

  None
  
* **Success Response:**

  * **Code:** 201 <br />
    **Content:** 
    ```javascript
      {
        "albumId": 1,
        "id": 1,
        "title": "accusamus beatae ad facilis cum similique qui sunt",
      }
    ```
 
* **Error Response:**

  * **Code:** 404 NOT FOUND <br />
    **Content:** `{ error : "File not found" }`

* **Sample Call:**

  ```javascript
    $.ajax({
      url: "/photos/1",
      dataType: "json",
      type : "DELETE",
      success : function(r) {
        console.log(r);
      }
    });
  ```