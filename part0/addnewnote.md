::: mermaid
sequenceDiagram
    Participant B as Browser
    Participant S as Server

    B ->>+ S: Get https://studies.cs.helsinki.fi/exampleapp/notes;
    S -->>- B: Returns HTML Document;
    B ->>+ S: Get https://studies.cs.helsinki.fi/exampleapp/main.css;
    S -->>- B: The CSS File;
    B ->>+ S: Get https://studies.cs.helsinki.fi/exampleapp/main.js;
    S -->>- B: The Javascript File;
    Note right of B: The browser executes the JavaScript code that fetches the JSON file from the server;
    B ->>+ S: GET https://studies.cs.helsinki.fi/exampleapp/data.json;
    S -->>- B: [The notes Page is displayed];
    Note right of B: The Browser executes the call back function that renders the note;
    %% When the data has been fetched, the browser executes an event handler, which renders the notes to the page using the DOM-API.
    %%To add New Note
    %% User enters data in the Input Box , then clicks the Button
    B ->>+ S: Post https://studies.cs.helsinki.fi/exampleapp/new_note;
    Note right of B: When the button on the form is clicked, the browser will send the user input to the server;
    S -->>- B: HTTP status code 302.;
    Note right of B: The server responds with HTTP status code 302.;
:::