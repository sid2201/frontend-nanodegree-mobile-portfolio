## Website Performance Optimization portfolio project

### About

The objective of this project is to optimize [Cameron Pittman's portfolio](https://github.com/sid2201/frontend-nanodegree-mobile-portfolio) page for speed. The strategy is to optimize the critical rendering path, making the page render as quickly as possible, using techniques picked up in the Website Performance Optimization course.


### Page load speed optimization

- Image compression: images were rescaled and resized to the final layout dimensions.
- Inline critical CSS: critical above-the-fold content styles are inlined and applied to the document immediately which eliminated render blocking CSS.
- Defer alternative media CSS: print stylesheets. A media attribute was added to ensure that it would only be downloaded when printing.
- Minifying CSS/JS: all CSS and JS files were minified.


### Frame rate optimization

- As per Cameron's tip Forced Synchronous Layout is avoided while resizing the pizzas. This is
done by removing the function which calculated the dx value and instead wrote a function which 
resized the pizzas based on % values instead of px.
- Loop optimization: unnecessary JS operations were pulled out of `for` loops where possible, in `views/js/main.js`.
- Debouncing: scroll events were 'debounced' to decouple the animations and only reflow/repaint when needed.

### Running instructions

 - Unzip the folder
 - You can run the page by clicking on index.html
 - To inspect the site on your phone, you can run a local server

  ```bash
  $> cd /path/to/your-project-folder
  $> python -m SimpleHTTPServer 8080
  ```

 - Open a browser and visit localhost:8080
 - Download and install [ngrok](https://ngrok.com/) to make your local server accessible remotely.

  ``` bash
  $> cd /path/to/your-project-folder
  $> ngrok 8080
  ```

 - Copy the public URL ngrok gives you and try running it through PageSpeed Insights!

