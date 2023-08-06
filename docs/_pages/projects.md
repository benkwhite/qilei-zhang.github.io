---
permalink: /projects/
author_profile: true
layout: single
toc: true
toc_sticky: true
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
        bottom: 280px;
        right: 15px;
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
        font-size: 0.6em;
        font-style: italic;
        text-align: center;
        padding: 5px;
        order-radius: 5px;
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
        if ($(this).scrollTop() > 600) {
            $('#back-to-top').fadeIn();
        } else {
            $('#back-to-top').fadeOut();
        }
      });
      $('#back-to-top').click(function() {
        $("html, body").animate({ scrollTop: 0 }, 600);
        $(this).fadeOut();
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
  <a href="{{ '/projects/seats/' | relative_url }}"><button class="pdf-button">Readme</button></a>
  <a href="https://github.com/benkwhite"><button class="pdf-button">Code (Release Soon)</button></a>
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

## Advanced Flight Data Analysis and Phase Identification

<div class="project-section">
  <!-- <h3>Airlines Seats Prediction and Competition Analysis</h3> -->
  <!-- project time, role, location -->
  <p class="smaller-text">Project Time: Sep 2020 - May 2024</p>
  <p class="smaller-text">Role: Project Lead</p>
  <p class="smaller-text">Location: West Lafayette, IN</p>
  
  <p class="smaller-text">The Advanced Flight Data Analysis and Phase Identification project is a pioneering initiative leveraging machine learning techniques and data preprocessing to address issues related to operational data analysis at general aviation airports. The project employs a novel algorithm to identify and classify different aircraft trajectories into flight phases. This approach improves classification performance by over 20%, allowing for more precise noise and emission modeling, ultimately helping address public concerns about airports.</p>
  
  <!-- buttons for reports and code links, and etc -->
  <a href="https://doi.org/10.1109/TITS.2021.3106774"><button class="pdf-button">Paper 1</button></a>
  <a href="https://doi.org/10.1177/03611981221127016"><button class="pdf-button">Paper 2</button></a>
  <a href="https://purr.purdue.edu/publications/3852/1"><button class="pdf-button">Data</button></a>
  <!-- <a href="{{ '/assets/pdf/SeatPred.pdf' | relative_url }}"><button class="pdf-button">Slides</button></a> -->
  <button class="pdf-button collapsible">Details</button>
  <div class="content">
    <p> The project focuses on the potential of Automatic Dependent Surveillance-Broadcast (ADS-B) data, using machine learning to decode operational details from this data, leading to improved noise and emissions models. This process involves preprocessing flight records, incorporating meteorological data and other factors, to improve data accuracy and completeness. These efforts are particularly aimed at general aviation airports, which typically lack comprehensive operational data.</p>

    <p> A core achievement of this project is the development of an algorithm that combines supervised and unsupervised machine learning techniques to classify aircraft trajectories into different flight phases. Compared to traditional methods, this approach significantly improves classification performance, demonstrating over a 20% enhancement in accuracy. This advancement is vital for better noise and emission modeling, directly addressing public concerns related to airports.</p>

    <p> This research led to the successful creation of a framework capable of identifying different flight phases, solving significant problems faced in flight data mining. This new methodological approach was tested and validated using synthetic and empirical ADS-B data, and it showed promising results, positioning it as a feasible solution for deployment in airport operations. The identification of flight phases provides essential data for understanding aircraft operations and their environmental impact, enabling stakeholders to take meaningful action to reduce perceived environmental damage from noise and emissions. </p>

    <p> Finally, the project lays groundwork for future research, proposing the development of a neural network structure that combines the Recurrent Neural Network (RNN) and Generative adversarial network (GAN). This network is designed to process sequential input data and generate missing flight maneuvering event records, reconstructing operational aircraft trajectories into a consecutively spaced data series. The ultimate goal is to develop a system that can provide real-time flight status data to airport managers, aiding in airport planning and facilitating accurate input into airport evaluation tools and environmental studies. </p>

    <figure>
    <video width="500" height="500" controls>
      <source src="{{ '/assets/video/adsb_sim.mp4' | relative_url }}" type="video/mp4">
      Your browser does not support the video tag.
    </video>
    <figcaption class="figure-caption">Demo of ADS-B Simulation.</figcaption>
    </figure>
  </div>
  
  <!-- Add picture caption and option to adjust image size -->
  <figure>
    <img class="project-img" src="{{ '/assets/images/zhang1.png' | relative_url }}" alt="This flow chart is from my first publication. Check more detailed explanation in Paper.">
    <figcaption>Flowchart of the methodology in first step of the Flight Phase Identification.</figcaption>
  </figure>
</div>

<!-- <a href="#top" id="back-to-top" class="back-to-top" style="display: none;"> <b style="color:#FFFFFF font-size: 14px"> &#8593; Top </b></a> -->

<!-- - Employed preprocessing techniques on flight records, incorporating meteorological data and other factors, to enhance data accuracy and completeness, enabling better analysis of operations at general aviation airports.
- Drawing inspiration from NLP techniques, such as Transformer and BERT, to process time-series flight data, thereby repairing, supplementing, and improving the integrity and reliability of data for advanced analysis.
- Developed a novel algorithm with supervised and unsupervised machine learning techniques to classify aircraft trajectories into different phases, resulting in a performance improvement of over 20% compared to traditional methods, leading to better noise and emission modeling and addressing public concerns related to airports. -->

## Enhancing Commuting with Optimized Vertiport Distribution and Demand Estimation

<div class="project-section">
  <!-- <h3>Airlines Seats Prediction and Competition Analysis</h3> -->
  <!-- project time, role, location -->
  <p class="smaller-text">Project Time: Aug 2022 - Jan 2023</p>
  <p class="smaller-text">Role: Project Lead</p>
  <p class="smaller-text">Location: West Lafayette, IN</p>
  
  <p class="smaller-text">This project offered a dedicated analysis of the potential demand for Urban Air Mobility (UAM) operations, particularly concerning vertiport placement and the desired number of vertiports. The study explores the feasibility of UAM operations in Chicago, illustrating the time-saving benefits of eVTOL trips and providing a solid forecast for stakeholders about this emerging air transportation market. The results reveal UAM's competitive edge and potential to significantly enhance the transportation system's efficiency and equity.</p>
  
  <!-- buttons for reports and code links, and etc -->
  <a href="https://doi.org/10.2514/6.2023-3262"><button class="pdf-button">Paper</button></a>
  <!-- <a href="https://doi.org/10.1177/03611981221127016"><button class="pdf-button">PDF 2</button></a> -->
  <!-- <a href="https://purr.purdue.edu/publications/3852/1"><button class="pdf-button">Data</button></a> -->
  <a href="{{ '/assets/pdf/2023_AIAA_UAM_DIS_Chicago.pdf' | relative_url }}"><button class="pdf-button">Slides</button></a>
  <a href="https://github.com/benkwhite"><button class="pdf-button">Code (Release Soon)</button></a>
  <button class="pdf-button collapsible">Details</button>
  <div class="content">
    <p> Urban Air Mobility (UAM) concepts have obtained substantial attention in recent years due to their potential to offer an alternative mode of daily transport and alleviate issues such as traffic congestion and environmental pollution. This project, centered around UAM operations, carries out a dedicated analysis of the potential demand within a specific range, which is critical to determining the placement and optimal number of vertiports. The focus of this investigation was the Chicago metropolitan area, a densely populated urban region considered an ideal candidate for such novel air transportation services.</p>

    <p> By assessing the commuting demand in Chicago, the research provides valuable insights into the feasibility of UAM operations and vertiports distribution. The study applies techniques that quantify the benefits brought by UAM, with a particular focus on the time-saving advantages of eVTOL trips compared to traditional driving commutes. The results highlight how competitive the UAM network can be, thereby aiding UAM stakeholders in understanding the prospective market for this innovative transportation modality.</p>

    <p> Additionally, the research underscores the necessity for more comprehensive market evaluations, including more subjective surveys, alongside the objective census data utilized. Collecting additional opinions from policymakers, surrounding communities, and operators are advised, to ensure that benefits for both users and non-users are considered. </p>

    <p> The project also identifies the need for an optimization program to examine vertiport placement more closely and the introduction of a critical constraint, such as vertiport capacity, into the design of this new transportation system. Ultimately, this project argues that UAM should demonstrate the benefits it can bring to the public and promote an efficient and equitable transportation system that provides a convenient and affordable form of transportation for each trip. The study's findings offer a robust forecast for UAM stakeholders and a foundation for future research and developments in this emerging field. </p>

    <!-- Add picture caption and option to adjust image size -->
  <figure>
    <img class="project-img" src="{{ '/assets/images/histshift.png' | relative_url }}" alt="Density Distribution of Trip Time Shift Based on 100 Vertiports Simulation.">
    <figcaption>Density Distribution of Trip Time Shift Based on 100 Vertiports Simulation.</figcaption>
  </figure>
  </div>
</div>


## Pilot Performance Analyses and Training Evaluation for Inflight Safety
<div class="project-section">
  <!-- <h3>Airlines Seats Prediction and Competition Analysis</h3> -->
  <!-- project time, role, location -->
  <p class="smaller-text">Project Time: May 2022 - Aug 2022</p>
  <p class="smaller-text">Role: Project Lead</p>
  <p class="smaller-text">Location: West Lafayette, IN</p>
  
  <p class="smaller-text">This project centered on investigating Loss of Control In-flight (LOC-I) accidents with the aim of devising ways to mitigate future occurrences. The project has identified energy management as a key factor in LOC-I incidents and is now focused on developing a suite of maneuvers training that could potentially be included in pilot training to prevent LOC-I. Experimental data collection will be used, with pilots divided into control and experimental groups, each receiving different energy management training. This data will be analyzed using CloudAhoy and fuzzy logic to evaluate the pilots' performance and the effectiveness of the training interventions.</p>
  
  <!-- buttons for reports and code links, and etc -->
  <a href="{{ '/assets/pdf/PilotPerf.pdf' | relative_url }}"><button class="pdf-button">Report</button></a>
  <!-- <a href="https://doi.org/10.1177/03611981221127016"><button class="pdf-button">PDF 2</button></a> -->
  <!-- <a href="https://purr.purdue.edu/publications/3852/1"><button class="pdf-button">Data</button></a> -->
  <a href="https://github.com/benkwhite"><button class="pdf-button">Code (Release Soon)</button></a>
  <button class="pdf-button collapsible">Details</button>
  <div class="content">
    <p> The project's primary purpose is to study LOC-I accidents, which are a significant concern in aviation safety. LOC-I accidents, often resulting from a pilot’s inability to accurately assess, comprehend, and control the energy state of the aircraft, are typically fatal. Through a comprehensive meta-analysis of reported LOC-I accidents, the researchers identified energy management as a pivotal factor in these occurrences.</p>

    <p> The project involves analyzing different training maneuvers to determine if it's possible to devise a specific maneuver or a suite of maneuver training to mitigate LOC-I. This initiative is aimed at enhancing pilots' understanding and control over the energy state of their aircraft. The pilots were divided into three groups: one control group and three experimental groups. The three experimental groups will receive distinct interventions in terms of energy management training. The post-test flight, similar to the pre-test, will help determine whether the training interventions had any statistically significant impact on the energy management capability of the groups.</p>

    <p> To evaluate pilot performance, fuzzy logic is applied, offering a degree of correctness compared to the instructions, thus determining how close the current status is to the desired one. The report notes that the training might help improve the lower limit of performance but may not have a significant impact on the upper limit. </p>

    <p> Lastly, the project's report discusses the impacts of different training videos on the pilot groups, noting improvements in some and lesser changes in others. The report also acknowledges limitations due to the limited sample size and notes that many factors, such as pilot interactions or additional research by the pilots, could have immeasurable effects on the experiment. </p>

    <!-- Add picture caption and option to adjust image size -->
  <figure>
    <img class="project-img" src="{{ '/assets/images/fuzzy_example.png' | relative_url }}" alt="The connection between numerical input and its membership.">
    <figcaption>Fuzzy logic membership (the process of designing evaluation metrics).</figcaption>
  </figure>
  </div>
</div>

## Advanced Image Processing and Optimization Solutions in AI Applications
<div class="project-section">
  <!-- project time, role, location -->
  <p class="smaller-text">Project Time: Aug 2021 - May 2022</p>
  <!-- <p class="smaller-text">Role: Project Lead</p> -->
  <p class="smaller-text">Location: West Lafayette, IN</p>
  
  <p class="smaller-text">Designed object classification, detection and localization models using convolutional and skip block networks, as well as independently implemented YOLO architecture, achieving accurate results on the COCO dataset. Additionally, generated realistic images with GANs using the CelebA dataset.</p>
  
  <!-- buttons for reports and code links, and etc -->
  <a href="{{ '/assets/pdf/ece695notes2.pdf' | relative_url }}"><button class="pdf-button">Example Report</button></a>
  <button class="pdf-button collapsible">Details</button>
  <div class="content">
    <p> The goal of the first project is to understand the usage of YOLO algorithm. The full name for YOLO is You Only Look Once. It is useful for detecting and localizing for multi-instance object. It improves detection accuracy and speed compared to traditional detection schemes. It treats object detection as one regression problem, so it is also called a one-stage algorithm. The image is divided into a grid of cells and the job of predicting the bounding-box and the class-label for an object in the image is the responsibility of the grid cell that has the center of the object in it. The project used YOLO to apply in the COCO images.</p>

    <p> The goal of the second project is to understand the usage of generative adversarial network (GAN). GANs are a framework for teaching a DL model to capture the training data’s distribution so model can generate new data from that same distribution. They are made of two distinct models, a generator and a discriminator. Particularly, generator code will use Transpose Convolutions to expand noise vectors into images that will look very similar to the images in the training data. The project used CelebFaces Attributes Dataset that contains thousands of celebrity images. The expected objective of the project is to produce images will look very similar to the training images without being exactly the same as any of them.</p>

    <!-- Add picture caption and option to adjust image size -->
  <figure>
    <img class="project-img" src="{{ '/assets/images/elephant_example.png' | relative_url }}" alt="The connection between numerical input and its membership.">
    <figcaption>Annotated and predicted image examples.</figcaption>
  </figure>
  </div>

  <figure>
    <img class="project-img" src="{{ '/assets/images/fakeimages.png' | relative_url }}" alt="Fake human faces generated by GAN ne.">
    <figcaption>Fake human faces generated by GAN net.</figcaption>
  </figure>
</div>

## Study on the Solution of Traveller Salesman Problem with Deep Reinforcement Learning
<div class="project-section">
  <!-- project time, role, location -->
  <p class="smaller-text">Project Time: Aug 2021 - May 2022</p>
  <!-- <p class="smaller-text">Role: Project Lead</p> -->
  <p class="smaller-text">Location: West Lafayette, IN</p>
  
  <p class="smaller-text">Working with my teammate <a href="https://www.cs.purdue.edu/people/graduate-students/bai123.html">Site Bai</a>, Deep Reinforcement Learning was applied to solve the Traveler Salesman Problem and two TSP variants with constraints. Firstly, we identified S2V-DQN as the state-of-the-art Deep RL algorithms that combines Graph Neural Networks to solve the TSP, re-implemented it in PyTorch and achieved identical results reported in the original paper. Secondly, we apply S2V-DQN to solve the TSP with Time Windows and achieved comparable results with other operations research tools. Thirdly, we test the performance of S2V-DQN on the TSP with Pickup and Delivery, and the results are unsatisfying. We analyze the reason may be that the brute-force masking scheme on the output layer is not enough for com- plex constraints, which may need elaborate design to be intrinsically embedded into the deep networks.
</p>
  
  <!-- buttons for reports and code links, and etc -->
  <a href="{{ '/assets/pdf/cs578report.pdf' | relative_url }}"><button class="pdf-button">Report</button></a>
  <button class="pdf-button collapsible">Details</button>
  <div class="content">
    <p> In this project, we studied how to apply Deep Reinforcement Learning to solve the Traveler Salesman Problem. Specifically, we identified S2V-DQN as the state-of-the- art Deep RL algorithms that combines Graph Neural Networks to solve the problem, re-implemented it in PyTorch and achieved identical results reported in the original paper. Moreover, we applied S2V-DQN to solve the TSP with simple constraints like TSP with Time Windows and found it effective regarding problem of this kind. We also explored the performance of S2V-DQN on the TSP with more complex constraints like the TSP with Pickup and Delivery, and reported unsatisfying results. We analyzed that the cause may be imposing the brute-force masking scheme on the output layer while the problem itself may need elaborate design of the deep networks that can intrinsically embed the constraints. This points out the future direction of this work and many other on-going works are also good references.</p>

    <!-- Add picture caption and option to adjust image size -->
  <figure>
    <img class="project-img" src="{{ '/assets/images/cs578report.png' | relative_url }}" alt="Model of S2V-DQN.">
    <figcaption>Model of S2V-DQN.</figcaption>
  </figure>
  </div>
</div>


## Bike-sharing system demand factors analysis and prediction
- Analyzed the factors that affect the demand for bike-sharing systems, such as weather, time, and location, and developed a model to predict the number of bikes needed at each station.

<a href="{{ '/assets/pdf/SeatPred.pdf' | relative_url }}"><button class="pdf-button">Report</button></a>

## Imaginary Surface Integration and Airspace Design for eVTOL Operation Safety
- Designed a comprehensive vertiport safety envelope for Urban Air Mobility (UAM) and optimized its urban airspace for efficient and safe operation of electric Vertical Take-off and Landing (eVTOL) aircraft.
- Created a cutting-edge simulation model that determined the most efficient eVTOL routes while taking into account both urban airspace and ATC limitations, improving safety and operational efficiency.

<a href="{{ '/assets/pdf/SeatPred.pdf' | relative_url }}"><button class="pdf-button">Report</button></a>


<figure>
  <video width="576" height="324" controls>
    <source src="{{ '/assets/video/ImaginarySurface.mp4' | relative_url }}" type="video/mp4">
    Your browser does not support the video tag.
  </video>
  <figcaption class="figure-caption">An imaginaray surface and eVTOL operation demonstration.</figcaption>
</figure>


<!-- ## Checkout the Publication Page -->

