# Netflix Coding Challenge

##How to Start the App
I was having a bit of trouble getting "npm-start" to run webpack and my node server at the same time, so this process is inelegant (would definitely fix given a bit more time for research).

To start the app:


## Technologies Used
I used 4 main external libraries: Material-UI, React, Redux, and Node. I also used some supporting modules (middleware, etc).

##General Process
I first thought about the app as a whole and determined what data I would need, and what views would represent that data.

The App broke down into 2 main components: a search form and a "list" view where the search results would be rendered.

The only piece of "App-level" state I used was a searchResults reducer. In a more complex app, I might also have used Redux to store the searched term, but, since the term was only needed to make one external API call, I decided it was not necessary to create a reducer for that piece of state.

## Pain Points
1. CSS -- If I could do this project again, I probably wouldn't use Material-UI. It was good practice to use an external component library, but it made custom CSS difficult to inject. I had to do all of my CSS inline rather than in a stylesheet so it would override the Material-UI CSS. It also made color customization quite difficult, as it required modifying the theme provided by Material-UI and passing that theme to all components. That said, I think it still looks ok, but I can do better! :)

2. Movie Images -- The "poster" URLs returned by the API for some of the movie objects were dead links, so some movies don't have images associated with them. I tried to render a "stock" image as a fallback in these cases but was unable to do so. Given more time, I would have checked the file type of what the HTTP request was returning. If it wasn't returning an image, I would know I had a dead link and would render something else instead.

3. Form Control / Error Handling -- I didn't have as much time as I would have liked to implement form control on the front-end or error handling on the API call. On the front-end, I would use something more elegant than "alert()" to notify the user of form errors. On the back-end, I would have used status codes to handle errors rather than string responses from the server. That said, handling API errors in Redux is never that elegant.

4. Search result sort -- Currently, search results are ranked by rating. Next on my list of things to do was to add a dropdown that allowed users to sort
by other characteristics.