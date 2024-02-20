<script>
    import { onMount } from 'svelte';
    import * as d3 from 'd3';
    import Graph from './graph.svelte'; // Importing the Graph component
  
    let data = [];

  </script>
  
  <main>
    <h1>Traffic Collisions in San Diego</h1>
    <!-- Using the Graph component -->
    <Graph {data} />

    <div>
    <h3>Writeup</h3>
<p class="writeup">
    Our main plot is a line plot with a encodings of color for car maker and x, y for year and amount of injuries. We chose it because
    even though other types of plots such as scatter, or bar charts would be able to display the same information, but in
a much more crowded way. It would lead to a pretty confusing visualization that would probably confuse the
audience. Another one of our choices was to include a pie chart that would help to show the total number of 
accidents per vehicle and serve as a legend and filter. The pie chart was made to hover over and that way
you could filter out each line based on the portion of the pie chart that you hover over. Next, we added a 
filter for the year, that way you could go to specific years and see the lines more clearly. Another 
function of our graph was the ability to drag and zoom. This would allow the user to drag and filter based
off a certain time frame that they wanted to inspect more closely purely off of the visualization. The 
year filter is great for allowing a general range of years to be filtered while the drag function allows
the user to more closely inspect things about the visualization that they found interesting. The 
alternatives that we considered was a scatterplot of the data that filtered each accident based off of a 
car brand. This proved troublesome because not only was it very hard to visualize, but it was taking too 
much memory and ran very slowly. We eventually came to the conclusion that aggregating by the year and 
creating a line chart would allow us to portray all the information that we wanted, while allowing for 
filtering based off of year and help support our interactive pie chart that served as a legend.
</p>
<br class="writeup">
<p class="writeup">
    For our visualization, we had a dataset of vehicle collisions in San Diego. In our csv file, we had
the locations of the accidents, the vehicle makes and brands as well as the time of the accident. Our 
first idea was to plot a scatterplot for all the accidents based off the time. We split up the work, by 
deciding what tasks were going to be needed for the visualization and who was going to do each task. The 
code was passed between the two of us multiple times, each of us adding things as we needed and improving 
the visualization as we saw fit. It started off with our scatterplot and the pie chart being made. Both 
took time, and we each did one of those visualizations. This initial way of loading in the data and
plotting both graphs took around 4 hours. Then, we decided to add a year filter this took longer because 
of the way that we had to clean up the time data and figure out how to filter around 3 hours. Next, the
visualization was taking a long time to load with the scatterplot and so we decided that instead we should just 
aggregate the data by year and brand and add hover functions to the pie chart in order to see each brand
in the line chart. This took a huge amount of time around 10 hours total for all of these major edits. 
After this was done, a drag function was implemented and this would allow the user to filter based off of
interesting trends they saw. This took another 4 hours to complete. Overall it was a very time consuming 
project and the work was split pretty fairly among us both.
</p>
    </div>
    
  </main>
  
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Nunito:wght@300;400;700&display=swap');
  
    :root {
      --color-bg: #ffffff;
      --color-outline: #c2c2c2;
      --color-shadow: hsl(0, 0%, 0%, 0.1);
      --color-text: #3f4252;
      --color-bg-1: hsla(0, 0%, 0%, 0.2);
      --color-shadow-1: hsl(0, 0%, 96%);
    }
  
    *,
    *::before,
    *::after {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
  
    main {
      text-align: center;
      font-family: 'Nunito', sans-serif;
      font-weight: 300;
      line-height: 2;
      font-size: 24px;
      color: var(--color-text);
    }

    .writeup {
      text-align: left;
      font-family: 'Nunito', sans-serif;
      font-weight: 300;
      line-height: 1;
      font-size: 16;
      color: var(--color-text);
    }

  
    h1 {
      font-size: 2em;
      font-weight: 300;
      line-height: 2;
    }
  </style>
  