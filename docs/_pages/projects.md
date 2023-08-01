---
permalink: /projects/
author_profile: true
layout: single
toc: true
---
<!-- <i class="fa-solid fa-list-check"></i> -->

<head>
  <style>
    .project-section {
      background-color: white;
      padding: 20px;
      margin: 20px 0;
      border-radius: 10px;
    }
    .smaller-text {
        font-size: 18px !important;
    }
    /* .pdf-button {
      background-color: #4CAF50;
      border: none;
      color: white;
      padding: 15px 32px;
      text-align: center;
      text-decoration: none;
      display: inline-block;
      font-size: 16px;
      margin: 4px 2px;
      cursor: pointer;
    } */
    .pdf-button {
        background-color: #f8f8f8;
        color: #333;
        border: none;
        padding: 10px 20px;
        text-align: center;
        text-decoration: none;
        display: inline-block;
        font-size: 14px;
        margin: 3px 1px;
        transition-duration: 0.4s;
        border-radius: 10px;
        cursor: pointer;
        }
    .pdf-button:hover {
        background-color: #ddd;
        }
    .project-img {
      width: 100%; /* You can adjust this value */
      height: auto;
    }
    /* Style the button that is used to open and close the collapsible content */
    .collapsible {
      background-color: #9f9f9f;
      color: white;
      cursor: pointer;
      padding: 18px;
      width: 100%;
      border: none;
      text-align: left;
      outline: none;
      font-size: 16px;
    }
    /* img {
    max-width: 100%;
    height: auto;
    } */
    /* Add a background color to the button if it is clicked on (add the .active class with JS), and when you move the mouse over it (hover) */
    .active, .collapsible:hover {
      background-color: #555;
    }
    /* Style the collapsible content. Note: hidden by default */
    .content {
      padding: 0 18px;
      display: none;
      overflow: hidden;
      background-color: #f1f1f1;
    }
    .back-to-top {
        position: fixed;
        bottom: 25px;
        right: 25px;
        text-decoration: none;
        color: white !important;
        background-color: #1dbbe1; /* Modern blue */
        padding: 15px; /* Adjust the padding to make the button circle */
        border-radius: 30px; /* Make the button circle */
        display: none;
        transition: all 0.5s;
    }
    .back-to-top:hover {
        background-color: #00ceff; /* Darker blue */
    }
    figcaption {
        background-color: #f3f3f3; /* light gray */
        font-size: 0.9em;
        font-style: italic;
        text-align: center;
        padding: 5px;
    }
    
  </style>
  <!-- Include jQuery library -->
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
  <!-- Include custom JavaScript -->
  <script>
    $(document).ready(function(){
      $(".collapsible").click(function(){
        $(this).next(".content").slideToggle("slow");
      });
      $(window).scroll(function() {
        if ($(this).scrollTop() > 100) {
            $('#back-to-top').fadeIn();
        } else {
            $('#back-to-top').fadeOut();
        }
      });
      $('#back-to-top').click(function() {
        $("html, body").animate({ scrollTop: 0 }, 600);
        return false;
      });
    });
  </script>
</head>


# Projects

<!-- <h2>Projects</h2> -->
*Note: This page is still under construction. Please check back later.*
## Airlines Seats Prediction and Competition Analysis
<div class="project-section">
  <!-- <h3>Airlines Seats Prediction and Competition Analysis</h3> -->
  <!-- project time, role, location -->
  <p class="smaller-text">Project Time: Jun 2023 - Aug 2023</p>
  <!-- <p>Role: Project Lead</p> -->
  <p class="smaller-text">Location: Denver, CO</p>
  
  <p class="smaller-text">This project focuses on predicting the number of seats likely to be arranged for a given airline route in specified future quarters. The prediction model is built around Recurrent Neural Networks (RNN), which have shown effectiveness in dealing with sequential data. The historical dataset used for training the model has been sourced from Diio Mi, which consists of details related to airline performance and future schedules. It also introduced the other economic data, demographics data, etc.</p>

  <p class="smaller-text">The recurrent neural network architecture in the model incorporates various features including embeddings for categorical features, bidirectional recurrent layers (either GRU or LSTM), a self-attention mechanism, feed-forward layers with optional dropout, batch normalization, and an output layer that can either predict an output directly or predict a mean and standard deviation, depending on the chosen loss function.</p>
  
  <!-- buttons for reports and code links, and etc -->
  <a href="{{ '/assets/pdf/SeatPred.pdf' | relative_url }}"><button class="pdf-button">PDF</button></a>
  <button class="pdf-button collapsible">Details</button>
  <div class="content">
    <p> The initial architecture of the network is defined in the <code>__init__</code> function. Categorical features are first transformed into embedding vectors via embedding layers. Then, based on the specified choice, either a GRU or LSTM layer is used as the recurrent component of the network. The recurrent layer output is transformed by a linear layer, then passed through a self-attention mechanism. This is followed by two feed-forward layers (<code>fc1</code> and <code>fc2</code>) and batch normalization layers (<code>bn1</code> and <code>bn2</code>).</p>

    <p> During the forward propagation defined in <code>forward()</code>, the categorical features are embedded and concatenated with the continuous input features. This combined input is passed through the recurrent layer and transformed via a self-attention mechanism. If skip connections are enabled, the original output from the recurrent layer is added back to the attention-transformed output. The resultant output is passed through the feed-forward layers. Depending on whether MSE loss function is chosen, either an output value is directly predicted, or a mean and standard deviation are predicted.</p>

    <p> The <q>init_hidden</q> function is responsible for initializing the hidden states for the RNN layers. The dimensions of these hidden states are [num_layers * num_directions, batch_size, hidden_dim]. </p>

    <p> Overall, RNNNet offers a versatile RNN structure that supports various configurations and caters to a range of task requirements. Its functionality and adaptability make it a suitable choice for tasks involving sequential data with both categorical and continuous features.</p>
  </div>
  
  <!-- Add picture caption and option to adjust image size -->
  <figure>
    <img class="project-img" src="{{ '/assets/images/AS_EWRSEA_ind.png' | relative_url }}" alt="An example of Seat Prediction for Alaska Airlines (AS) for route EWR-SEA.">
    <figcaption>An example of Seat Prediction for Alaska Airlines (AS) for route EWR-SEA.</figcaption>
  </figure>
</div>

<a href="#top" id="back-to-top" class="back-to-top" style="display: none;"> <b style="color:#FFFFFF font-size: 14px"> &#8593; Top </b></a>

## Advanced Flight Data Analysis and Phase Identification for Emission Modeling

- Employed preprocessing techniques on flight records, incorporating meteorological data and other factors, to enhance data accuracy and completeness, enabling better analysis of operations at general aviation airports.
- Drawing inspiration from NLP techniques, such as Transformer and BERT, to process time-series flight data, thereby repairing, supplementing, and improving the integrity and reliability of data for advanced analysis.
- Developed a novel algorithm with supervised and unsupervised machine learning techniques to classify aircraft trajectories into different phases, resulting in a performance improvement of over 20% compared to traditional methods, leading to better noise and emission modeling and addressing public concerns related to airports.

## Enhancing Commuting with Optimized Vertiport Distribution and Demand Estimation
- Investigated the feasible distribution of vertiports for Urban Air Mobility (UAM) operations using a Grid Distance Based Clustering optimization method, considering commuting demand in the Chicago metropolitan area to maximize the benefits of this emerging transportation service.
- Optimized processing for millions of demographic data points by employing matrix and vectorization operations, utilizing Google Maps Routes API, and conducting random sampling modeling with neural networks and regression analysis before applying the model to the large population.
- Conducted benefit-cost analysis, revealing an equilibrium point that resulted in a time value saving of $00024;100M, demonstrating the effectiveness of UAM in reducing long-haul commute times.

## Pilot Performance Analyses and Training Evaluation for Inflight Safety
- Analyzed Inflight-Loss-of-Control accidents by assessing pilots' energy management performance, processing A/B test flight records into quantifiable scores using fuzzy logic, and enhancing accident evaluation.
- Developed performance metrics and conducted advanced statistical analyses with Python/Scipy, culminating in a technical report for the FAA, showcasing the impact of effective pilot training.

## Advanced Image Processing and Optimization Solutions in AI Applications
- Designed object detection and localization models using convolutional and skip block networks, as well as independently implemented YOLO architecture, achieving accurate results on the COCO dataset; Generated realistic images with GANs using the CelebA dataset.

## Study on the Solution of Traveller Salesman Problem with Deep Reinforcement Learning
- Working with teamates [Site Bai](https://www.cs.purdue.edu/people/graduate-students/bai123.html), we developed an S2V-DQN algorithm to efficiently solve TSP with time windows, attaining results comparable to traditional operations research tools.

## Bike-sharing system demand factors analysis and prediction
- Analyzed the factors that affect the demand for bike-sharing systems, such as weather, time, and location, and developed a model to predict the number of bikes needed at each station.

## Imaginary Surface Integration and Airspace Design for eVTOL Operation Safety
- Designed a comprehensive vertiport safety envelope for Urban Air Mobility (UAM) and optimized its urban airspace for efficient and safe operation of electric Vertical Take-off and Landing (eVTOL) aircraft.
- Created a cutting-edge simulation model that determined the most efficient eVTOL routes while taking into account both urban airspace and ATC limitations, improving safety and operational efficiency.



<!-- ## Checkout the Publication Page -->

