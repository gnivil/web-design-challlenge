# HTML/CSS Challenge - Web Visualization Dashboard (Latitude)

Use HTML and CSS to create a website showcasing weather data analyzed in the SQLAlchemy challenge.
In building this dashboard, we'll create individual pages for each plot and a means by which we can navigate between them. These pages will contain the visualizations and their corresponding explanations. We'll also have a landing page, a page where we can see a comparison of all of the plots, and another page where we can view the data used to build them.

The website must, at the top of every page, have a navigation menu that:
* Has the name of the site on the left of the nav which allows users to return to the landing page from any page
* Contains a dropdown menu on the right of the navbar named "Plots" that provides a link to each individual visualization page
* Provides two more text links on the right: "Comparisons," which links to the comparisons page, and "Data," which links to the data page
* Is responsive (using media queries). The nav must have similar behavior as the screenshots "Navigation Menu" section

-----
## Landing Page
* Contains an  explanation of the project.
* Links to each visualizations page
* Includes a sidebar containing preview images of each plot
* Clicking an image takes users to that visualization

![alt text](https://github.com/gnivil/HTML-CSS/blob/147e49519adad68e6f2c5d4f243ffece758589b1/Images/landingResize.png)

```html
<!DOCTYPE html>
<html lang="en-us">
  <head>

    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">

    <title>Bootstrap Visualization Dashboard</title>

    <!-- Boostrap Stylesheet -->
    <link rel="stylesheet" href="assets/css/bootstrap.min.css" media="screen">

    <!-- Our own CSS stylesheet -->
    <link rel="stylesheet" href="assets/css/styles.css" media="screen">

  </head>

  <body>
    <!-- Start of navbar -->
    <nav class="navbar navbar-default">
      <div class="container-fluid navbar-custom">

        <!-- Brand and toggle get grouped for better mobile display -->
        <div class="row">
          <div class="navbar-header">
            <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1" aria-expanded="false">
              <span class="sr-only">Toggle Navigation</span>
              <span class="icon-bar"></span>
              <span class="icon-bar"></span>
              <span class="icon-bar"></span>
            </button>
            <div class="col-xs-9 phone-nav">
              <a class="navbar-brand" href="#" id="logo">Latitude</a>
            </div>
          </div>

          <!-- Collect the nav links, forms, and other content for toggling -->
          <div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1">
            <ul class="nav navbar-nav navbar-right navbar-right-custom">
              <li class="dropdown">
                <a href="#" class="dropdown-toggle" data-toggle="dropdown" role="button" aria-haspopup="true" aria-expanded="false">Plots <span class="caret"></span></a>
                <ul class="dropdown-menu">
                 <li><a href="visualizations/temp.html">Max Temperature</a></li>
                  <li><a href="visualizations/humidity.html">Humidity</a></li>
                  <li><a href="visualizations/cloudiness.html">Cloudiness</a></li>
                  <li><a href="visualizations/wind.html">Wind Speed</a></li>
                </ul>
              </li>
              <li><a href="comparison.html">Comparison</a></li>
              <li><a href="data.html">Data</a></li>
            </ul>
          </div><!-- /.navbar-collapse -->
        </div>
      </div><!-- /.container-fluid -->
    </nav>
    <!-- End of navbar -->

    <!-- Start of container -->
    <div class="container">
      <section class="row">
        <div class="col-md-8">
          <article class="description-content">
            <h1 class="description-header">Summary: Latitude vs. X</h1>
            <hr class="description-hr"/>
            <img src="assets/images/Fig1.png" alt="" id="description-image"/>
            <p>The purpose of this project was to analyze how weather changes as you get closer to the equator. To accomplish this analysis, we first pulled data from the OpenWeatherMap API to assemble a dataset on over 500 cities.</p>
            <p>After assembling the dataset, we used Matplotlib to plot various aspects of the weather vs. latitude. Factors we looked at included: temperature, cloudiness, wind speed, and humidity. This site provides the source data and visualizations created as part of the analysis, as well as explanations and descriptions of any trends and correlations witnessed.</p>
          </article>
        </div>
        <div class="col-md-4">

          <!-- Start of Visualizations imageNav Area -->
          <section id="imageNav-area">
            <div class="imageNav-content">
              <h2 class="imageNav-header">Visualizations</h2>
              <hr />
              <div id="images">
                <a href="visualizations/temp.html"><img src="assets/images/Fig1.png" alt="Latitude vs. Max Temperature" class="imageNav-photo"></a>
                <a href="visualizations/humidity.html"><img src="assets/images/Fig2.png" alt="Latitude vs. Humidity" class="imageNav-photo"></a>
                <a href="visualizations/cloudiness.html"><img src="assets/images/Fig3.png" alt="Latitude vs. Cloudiness" class="imageNav-photo"></a>
                <a href="visualizations/wind.html"><img src="assets/images/Fig4.png" alt="Latitude vs. Wind Speed" class="imageNav-photo"></a>
              </div>
            </div>
          </section>
          <!-- End of the Visualizations imageNav Area -->

        </div>
      </section>
    </div>
    <!-- End of container -->

    <!-- Start of footer -->
    <footer class="footer navbar-fixed-bottom">
      <div class="two-toned-footer-color"></div>
      <p class="text-muted text-muted-footer text-center">
        &copy; Copyright Coding Bootcamp 2017
      </p>
    </footer>
    <!-- End of footer -->

    <!-- jQuery CDN -->
    <script type="text/javascript" src="https://code.jquery.com/jquery-2.1.4.min.js"></script>

    <!-- Bootstrap CDN -->
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/js/bootstrap.min.js"></script>
  </body>

</html>
```

-----

## Four Visualization Pages
* Descriptive title and heading tag
* Plot/visualization itself for the selected comparison
* A paragraph describing the plot and its significance

![alt text](https://github.com/gnivil/HTML-CSS/blob/621322d23f1df9e8eb7d8f126952343beffa6924/Images/visualize-lg.png)

###### Max Temperature
```html
<!DOCTYPE html>
<html lang="en-us">

<head>

  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">

  <title>Bootstrap Visualization Dashboard</title>

  <!-- Boostrap Stylesheet -->
  <link rel="stylesheet" href="../assets/css/bootstrap.min.css" media="screen">

  <!-- Our own CSS stylesheet -->
  <link rel="stylesheet" href="../assets/css/styles.css" media="screen">

</head>

<body>
  <!-- Start of navbar -->
  <nav class="navbar navbar-default">
    <div class="container-fluid navbar-custom">

      <!-- Brand and toggle get grouped for better mobile display -->
      <div class="row">
        <div class="navbar-header">
          <button type="button" class="navbar-toggle collapsed" data-toggle="collapse"
            data-target="#bs-example-navbar-collapse-1" aria-expanded="false">
            <span class="sr-only">Toggle Navigation</span>
            <span class="icon-bar"></span>
            <span class="icon-bar"></span>
            <span class="icon-bar"></span>
          </button>
          <div class="col-xs-9 phone-nav">
            <a class="navbar-brand" href="../index.html" id="logo">Latitude</a>
          </div>
        </div>

        <!-- Collect the nav links, forms, and other content for toggling -->
        <div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1">
          <ul class="nav navbar-nav navbar-right navbar-right-custom">
            <li class="dropdown">
              <a href="#" class="dropdown-toggle" data-toggle="dropdown" role="button" aria-haspopup="true"
                aria-expanded="false">Plots <span class="caret"></span></a>
              <ul class="dropdown-menu">
                <li><a href="temp.html">Max Temperature</a></li>
                <li><a href="humidity.html">Humidity</a></li>
                <li><a href="cloudiness.html">Cloudiness</a></li>
                <li><a href="wind.html">Wind Speed</a></li>
              </ul>
            </li>
            <li><a href="../comparison.html">Comparison</a></li>
            <li><a href="../data.html">Data</a></li>
          </ul>
        </div><!-- /.navbar-collapse -->
      </div>
    </div><!-- /.container-fluid -->
  </nav>
  <!-- End of navbar -->

  <!-- Start of container -->
  <div class="container">
    <section class="row">
      <div class="col-md-8">
        <article class="description-content">
          <h1 class="description-header">Max Temperature</h1>
          <hr class="description-hr" />
          <img src="../assets/images/Fig1.png" alt="" class="img-responsive" />
          <p>As expected, the weather becomes significantly warmer as one approaches the equator (0 Deg. Latitude). More
            interestingly, however, the northern hemisphere tends to have a higher max temperature than the southern
            hemisphere at 20 degrees removed from the equator. This may be due to the tilt of the earth at the time of
            the year this data was gathered.</p>
        </article>
      </div>
      <div class="col-md-4">

        <!-- Start of Visualizations imageNav Area -->
        <section id="imageNav-area">
          <div class="imageNav-content">
            <h2 class="imageNav-header">Visualizations</h2>
            <hr />
            <div id="images">
              <a href="temp.html"><img src="../assets/images/Fig1.png" alt="Latitude vs. Max Temperature"
                  class="imageNav-photo active"></a>
              <a href="humidity.html"><img src="../assets/images/Fig2.png" alt="Latitude vs. Humidity"
                  class="imageNav-photo"></a>
              <a href="cloudiness.html"><img src="../assets/images/Fig3.png" alt="Latitude vs. Cloudiness"
                  class="imageNav-photo"></a>
              <a href="wind.html"><img src="../assets/images/Fig4.png" alt="Latitude vs. Wind Speed"
                  class="imageNav-photo"></a>
            </div>
          </div>
        </section>
        <!-- End of the Visualizations imageNav Area -->

      </div>
    </section>
  </div>
  <!-- End of container -->

  <!-- Start of footer -->
  <footer class="footer navbar-fixed-bottom">
    <div class="two-toned-footer-color"></div>
    <p class="text-muted text-muted-footer text-center">
      &copy; Copyright Coding Bootcamp 2017
    </p>
  </footer>
  <!-- End of footer -->

  <!-- jQuery CDN -->
  <script type="text/javascript" src="https://code.jquery.com/jquery-2.1.4.min.js"></script>

  <!-- Bootstrap CDN -->
  <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/js/bootstrap.min.js"></script>
</body>

</html>
```

###### Humidity
```html
<!DOCTYPE html>
<html lang="en-us">
  <head>

    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">

    <title>Bootstrap Visualization Dashboard</title>

    <!-- Boostrap Stylesheet -->
    <link rel="stylesheet" href="../assets/css/bootstrap.min.css" media="screen">

    <!-- Our own CSS stylesheet -->
    <link rel="stylesheet" href="../assets/css/styles.css" media="screen">

  </head>

  <body>
    <!-- Start of navbar -->
    <nav class="navbar navbar-default">
      <div class="container-fluid navbar-custom">

        <!-- Brand and toggle get grouped for better mobile display -->
        <div class="row">
          <div class="navbar-header">
            <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1" aria-expanded="false">
              <span class="sr-only">Toggle Navigation</span>
              <span class="icon-bar"></span>
              <span class="icon-bar"></span>
              <span class="icon-bar"></span>
            </button>
            <div class="col-xs-9 phone-nav">
              <a class="navbar-brand" href="../index.html" id="logo">Latitude</a>
            </div>
          </div>

          <!-- Collect the nav links, forms, and other content for toggling -->
          <div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1">
            <ul class="nav navbar-nav navbar-right navbar-right-custom">
              <li class="dropdown">
                <a href="#" class="dropdown-toggle" data-toggle="dropdown" role="button" aria-haspopup="true" aria-expanded="false">Plots <span class="caret"></span></a>
                <ul class="dropdown-menu">
                 <li><a href="temp.html">Max Temperature</a></li>
                  <li><a href="humidity.html">Humidity</a></li>
                  <li><a href="cloudiness.html">Cloudiness</a></li>
                  <li><a href="wind.html">Wind Speed</a></li>
                </ul>
              </li>
              <li><a href="../comparison.html">Comparison</a></li>
              <li><a href="../data.html">Data</a></li>
            </ul>
          </div><!-- /.navbar-collapse -->
        </div>
      </div><!-- /.container-fluid -->
    </nav>
    <!-- End of navbar -->

    <!-- Start of container -->
    <div class="container">
      <section class="row">
        <div class="col-md-8">
          <article class="description-content">
            <h1 class="description-header">Humidity</h1>
            <hr class="description-hr"/>
            <img src="../assets/images/Fig2.png" alt="" class="img-responsive"/>
            <p>With our current analysis, it is difficult to find any obvious correlation between latittude and humidity. There is a clear band of many data points at 100% humidity, and there do seem to be strong clusters of high humidity around the equator and in some other areas (e.g. a strong band of 0% humidity at latitude > 60). Further analysis is required.</p>
          </article>
        </div>
        <div class="col-md-4">

          <!-- Start of Visualizations imageNav Area -->
          <section id="imageNav-area">
            <div class="imageNav-content">
              <h2 class="imageNav-header">Visualizations</h2>
              <hr />
              <div id="images">
                <a href="temp.html"><img src="../assets/images/Fig1.png" alt="Latitude vs. Max Temperature" class="imageNav-photo"></a>
                <a href="humidity.html"><img src="../assets/images/Fig2.png" alt="Latitude vs. Humidity" class="imageNav-photo active"></a>
                <a href="cloudiness.html"><img src="../assets/images/Fig3.png" alt="Latitude vs. Cloudiness" class="imageNav-photo"></a>
                <a href="wind.html"><img src="../assets/images/Fig4.png" alt="Latitude vs. Wind Speed" class="imageNav-photo"></a>
              </div>
            </div>
          </section>
          <!-- End of the Visualizations imageNav Area -->

        </div>
      </section>
    </div>
    <!-- End of container -->

    <!-- Start of footer -->
    <footer class="footer navbar-fixed-bottom">
      <div class="two-toned-footer-color"></div>
      <p class="text-muted text-muted-footer text-center">
        &copy; Copyright Coding Bootcamp 2017
      </p>
    </footer>
    <!-- End of footer -->

    <!-- jQuery CDN -->
    <script type="text/javascript" src="https://code.jquery.com/jquery-2.1.4.min.js"></script>

    <!-- Bootstrap CDN -->
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/js/bootstrap.min.js"></script>
  </body>

</html>
```

###### Cloudiness
```html
<!DOCTYPE html>
<html lang="en-us">

<head>

  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">

  <title>Bootstrap Visualization Dashboard</title>

  <!-- Boostrap Stylesheet -->
  <link rel="stylesheet" href="../assets/css/bootstrap.min.css" media="screen">

  <!-- Our own CSS stylesheet -->
  <link rel="stylesheet" href="../assets/css/styles.css" media="screen">

</head>

<body>
  <!-- Start of navbar -->
  <nav class="navbar navbar-default">
    <div class="container-fluid navbar-custom">

      <!-- Brand and toggle get grouped for better mobile display -->
      <div class="row">
        <div class="navbar-header">
          <button type="button" class="navbar-toggle collapsed" data-toggle="collapse"
            data-target="#bs-example-navbar-collapse-1" aria-expanded="false">
            <span class="sr-only">Toggle Navigation</span>
            <span class="icon-bar"></span>
            <span class="icon-bar"></span>
            <span class="icon-bar"></span>
          </button>
          <div class="col-xs-9 phone-nav">
            <a class="navbar-brand" href="../index.html" id="logo">Latitude</a>
          </div>
        </div>

        <!-- Collect the nav links, forms, and other content for toggling -->
        <div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1">
          <ul class="nav navbar-nav navbar-right navbar-right-custom">
            <li class="dropdown">
              <a href="#" class="dropdown-toggle" data-toggle="dropdown" role="button" aria-haspopup="true"
                aria-expanded="false">Plots <span class="caret"></span></a>
              <ul class="dropdown-menu">
                <li><a href="temp.html">Max Temperature</a></li>
                <li><a href="humidity.html">Humidity</a></li>
                <li><a href="cloudiness.html">Cloudiness</a></li>
                <li><a href="wind.html">Wind Speed</a></li>
              </ul>
            </li>
            <li><a href="../comparison.html">Comparison</a></li>
            <li><a href="../data.html">Data</a></li>
          </ul>
        </div><!-- /.navbar-collapse -->
      </div>
    </div><!-- /.container-fluid -->
  </nav>
  <!-- End of navbar -->

  <!-- Start of container -->
  <div class="container">
    <section class="row">
      <div class="col-md-8">
        <article class="description-content">
          <h1 class="description-header">Cloudiness</h1>
          <hr class="description-hr" />
          <img src="../assets/images/Fig3.png" alt="" class="img-responsive" />
          <p>There is no strong relationship between latitude and cloudiness. However, it is interesting to see that a
            strong band of cities sits at 0, 80, and 90% cloudiness.</p>
        </article>
      </div>
      <div class="col-md-4">

        <!-- Start of Visualizations imageNav Area -->
        <section id="imageNav-area">
          <div class="imageNav-content">
            <h2 class="imageNav-header">Visualizations</h2>
            <hr />
            <div id="images">
              <a href="temp.html"><img src="../assets/images/Fig1.png" alt="Latitude vs. Max Temperature"
                  class="imageNav-photo"></a>
              <a href="humidity.html"><img src="../assets/images/Fig2.png" alt="Latitude vs. Humidity"
                  class="imageNav-photo"></a>
              <a href="cloudiness.html"><img src="../assets/images/Fig3.png" alt="Latitude vs. Cloudiness"
                  class="imageNav-photo active"></a>
              <a href="wind.html"><img src="../assets/images/Fig4.png" alt="Latitude vs. Wind Speed"
                  class="imageNav-photo"></a>
            </div>
          </div>
        </section>
        <!-- End of the Visualizations imageNav Area -->

      </div>
    </section>
  </div>
  <!-- End of container -->

  <!-- Start of footer -->
  <footer class="footer navbar-fixed-bottom">
    <div class="two-toned-footer-color"></div>
    <p class="text-muted text-muted-footer text-center">
      &copy; Copyright Coding Bootcamp 2017
    </p>
  </footer>
  <!-- End of footer -->

  <!-- jQuery CDN -->
  <script type="text/javascript" src="https://code.jquery.com/jquery-2.1.4.min.js"></script>

  <!-- Bootstrap CDN -->
  <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/js/bootstrap.min.js"></script>
</body>

</html>
```

###### Wind Speed
```html
<!DOCTYPE html>
<html lang="en-us">

<head>

  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">

  <title>Bootstrap Visualization Dashboard</title>

  <!-- Boostrap Stylesheet -->
  <link rel="stylesheet" href="../assets/css/bootstrap.min.css" media="screen">

  <!-- Our own CSS stylesheet -->
  <link rel="stylesheet" href="../assets/css/styles.css" media="screen">

</head>

<body>
  <!-- Start of navbar -->
  <nav class="navbar navbar-default">
    <div class="container-fluid navbar-custom">

      <!-- Brand and toggle get grouped for better mobile display -->
      <div class="row">
        <div class="navbar-header">
          <button type="button" class="navbar-toggle collapsed" data-toggle="collapse"
            data-target="#bs-example-navbar-collapse-1" aria-expanded="false">
            <span class="sr-only">Toggle Navigation</span>
            <span class="icon-bar"></span>
            <span class="icon-bar"></span>
            <span class="icon-bar"></span>
          </button>
          <div class="col-xs-9 phone-nav">
            <a class="navbar-brand" href="../index.html" id="logo">Latitude</a>
          </div>
        </div>

        <!-- Collect the nav links, forms, and other content for toggling -->
        <div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1">
          <ul class="nav navbar-nav navbar-right navbar-right-custom">
            <li class="dropdown">
              <a href="#" class="dropdown-toggle" data-toggle="dropdown" role="button" aria-haspopup="true"
                aria-expanded="false">Plots <span class="caret"></span></a>
              <ul class="dropdown-menu">
                <li><a href="temp.html">Max Temperature</a></li>
                <li><a href="humidity.html">Humidity</a></li>
                <li><a href="cloudiness.html">Cloudiness</a></li>
                <li><a href="wind.html">Wind Speed</a></li>
              </ul>
            </li>
            <li><a href="../comparison.html">Comparison</a></li>
            <li><a href="../data.html">Data</a></li>
          </ul>
        </div><!-- /.navbar-collapse -->
      </div>
    </div><!-- /.container-fluid -->
  </nav>
  <!-- End of navbar -->

  <!-- Start of container -->
  <div class="container">
    <section class="row">
      <div class="col-md-8">
        <article class="description-content">
          <h1 class="description-header">Wind Speed</h1>
          <hr class="description-hr" />
          <img src="../assets/images/Fig4.png" alt="" class="img-responsive" />
          <p>With our current analysis, there is no obvious relationship between latitude and wind speed, so further
            analysis is needed. It is easy to see that there may be some correlation; notice that a larger number of
            cities in the northern hemisphere report over 20 mph of wind.</p>
        </article>
      </div>
      <div class="col-md-4">

        <!-- Start of Visualizations imageNav Area -->
        <section id="imageNav-area">
          <div class="imageNav-content">
            <h2 class="imageNav-header">Visualizations</h2>
            <hr />
            <div id="images">
              <a href="temp.html"><img src="../assets/images/Fig1.png" alt="Latitude vs. Max Temperature"
                  class="imageNav-photo"></a>
              <a href="humidity.html"><img src="../assets/images/Fig2.png" alt="Latitude vs. Humidity"
                  class="imageNav-photo"></a>
              <a href="cloudiness.html"><img src="../assets/images/Fig3.png" alt="Latitude vs. Cloudiness"
                  class="imageNav-photo"></a>
              <a href="wind.html"><img src="../assets/images/Fig4.png" alt="Latitude vs. Wind Speed"
                  class="imageNav-photo active"></a>
            </div>
          </div>
        </section>
        <!-- End of the Visualizations imageNav Area -->

      </div>
    </section>
  </div>
  <!-- End of container -->

  <!-- Start of footer -->
  <footer class="footer navbar-fixed-bottom">
    <div class="two-toned-footer-color"></div>
    <p class="text-muted text-muted-footer text-center">
      &copy; Copyright Coding Bootcamp 2017
    </p>
  </footer>
  <!-- End of footer -->

  <!-- jQuery CDN -->
  <script type="text/javascript" src="https://code.jquery.com/jquery-2.1.4.min.js"></script>

  <!-- Bootstrap CDN -->
  <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/js/bootstrap.min.js"></script>
</body>

</html>
```
-----

## Comparison Page
* Contains all of the visualizations on the same page to easily compare
* Uses a Bootstrap grid for the visualizations
* The grid must be two visualizations across on screens medium and larger, and 1 across on extra-small and small screens

![alt text](https://github.com/gnivil/HTML-CSS/blob/621322d23f1df9e8eb7d8f126952343beffa6924/Images/comparison-lg.png)

```html
<!DOCTYPE html>
<html lang="en-us">
  <head>

    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">

    <title>Bootstrap Visualization Dashboard</title>

    <!-- Boostrap Stylesheet -->
    <link rel="stylesheet" href="assets/css/bootstrap.min.css" media="screen">

    <!-- Our own CSS stylesheet -->
    <link rel="stylesheet" href="assets/css/styles.css" media="screen">

  </head>

  <body>
    <!-- Start of navbar -->
    <nav class="navbar navbar-default">
      <div class="container-fluid navbar-custom">

        <!-- Brand and toggle get grouped for better mobile display -->
        <div class="row">
          <div class="navbar-header">
            <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1" aria-expanded="false">
              <span class="sr-only">Toggle Navigation</span>
              <span class="icon-bar"></span>
              <span class="icon-bar"></span>
              <span class="icon-bar"></span>
            </button>
            <div class="col-xs-9 phone-nav">
              <a class="navbar-brand" href="index.html" id="logo">Latitude</a>
            </div>
          </div>

          <!-- Collect the nav links, forms, and other content for toggling -->
          <div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1">
            <ul class="nav navbar-nav navbar-right navbar-right-custom">
              <li class="dropdown">
                <a href="#" class="dropdown-toggle" data-toggle="dropdown" role="button" aria-haspopup="true" aria-expanded="false">Plots <span class="caret"></span></a>
                <ul class="dropdown-menu">
                 <li><a href="visualizations/temp.html">Max Temperature</a></li>
                  <li><a href="visualizations/humidity.html">Humidity</a></li>
                  <li><a href="visualizations/cloudiness.html">Cloudiness</a></li>
                  <li><a href="visualizations/wind.html">Wind Speed</a></li>
                </ul>
              </li>
              <li><a href="comparison.html">Comparison</a></li>
              <li><a href="data.html">Data</a></li>
            </ul>
          </div><!-- /.navbar-collapse -->
        </div>
      </div><!-- /.container-fluid -->
    </nav>
    <!-- End of navbar -->

    <!-- Start of container -->
    <div class="container">
      <article class="description-content row">
        <div class="col-xs-12">
          <h1 class="description-header">Comparison: Latitude vs X</h1>
          <hr class="description-hr"/>
          <p class="description-text">Click any plot to get an in-depth analysis.</p>
        </div>
        <div class="col-md-6">
          <h2 class="comparison-header">vs. Max Temperature</h2>
          <a href="visualizations/temp.html"><img src="assets/images/Fig1.png" alt="Latitude vs. Max Temperature" class="comparison-image img-responsive"></a>
          <hr class="visible-xs visible-sm">
        </div>
        <div class="col-md-6">
          <h2 class="comparison-header">vs. Humidity</h2>
          <a href="visualizations/humidity.html"><img src="assets/images/Fig2.png" alt="Latitude vs. Humidity" class="comparison-image img-responsive"></a>
          <hr class="visible-xs visible-sm">
        </div>
        <div class="col-md-6">
          <h2 class="comparison-header">vs. Cloudiness</h2>
          <a href="visualizations/cloudiness.html"><img src="assets/images/Fig3.png" alt="Latitude vs. Cloudiness" class="comparison-image img-responsive"></a>
          <hr class="visible-xs visible-sm">
        </div>
        <div class="col-md-6">
          <h2 class="comparison-header">vs. Wind Speed</h2>
          <a href="visualizations/wind.html"><img src="assets/images/Fig4.png" alt="Latitude vs. Wind Speed" class="comparison-image img-responsive"></a>
        </div>
      </article>
    </div>
    <!-- End of container  -->

    <!-- Start of footer -->
    <footer class="footer navbar-fixed-bottom">
      <div class="two-toned-footer-color"></div>
      <p class="text-muted text-muted-footer text-center">
        &copy; Copyright Coding Bootcamp 2017
      </p>
    </footer>
    <!-- End of footer -->

    <!-- jQuery CDN -->
    <script type="text/javascript" src="https://code.jquery.com/jquery-2.1.4.min.js"></script>

    <!-- Bootstrap CDN -->
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/js/bootstrap.min.js"></script>
  </body>

</html>
```

-----

## Data Page
* Displays a responsive table containing the data used in the visualizations
* The table must be a bootstrap table component

![alt text](https://github.com/gnivil/HTML-CSS/blob/621322d23f1df9e8eb7d8f126952343beffa6924/Images/data-lg.png)

```python
# import dependencies 
import os
import pandas as pd

# generate path to csv
csv_path = os.path.join('Resources', 'cities.csv')
cities_csv = pd.read_csv(csv_path)

# create html table and save to file 
cities_csv.to_html('table.html', index=False, classes=['table', 'table-striped', 'table-hover'])
```

```html
<!DOCTYPE html>
<html lang="en-us">
  <head>

    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">

    <title>Bootstrap Visualization Dashboard</title>

    <!-- Boostrap Stylesheet -->
    <link rel="stylesheet" href="assets/css/bootstrap.min.css" media="screen">

    <!-- Our own CSS stylesheet -->
    <link rel="stylesheet" href="assets/css/styles.css" media="screen">

  </head>

  <body>
    <!-- Start of navbar -->
    <nav class="navbar navbar-default">
      <div class="container-fluid navbar-custom">

        <!-- Brand and toggle get grouped for better mobile display -->
        <div class="row">
          <div class="navbar-header">
            <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1" aria-expanded="false">
              <span class="sr-only">Toggle Navigation</span>
              <span class="icon-bar"></span>
              <span class="icon-bar"></span>
              <span class="icon-bar"></span>
            </button>
            <div class="col-xs-9 phone-nav">
              <a class="navbar-brand" href="index.html" id="logo">Latitude</a>
            </div>
          </div>

          <!-- Collect the nav links, forms, and other content for toggling -->
          <div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1">
            <ul class="nav navbar-nav navbar-right navbar-right-custom">
              <li class="dropdown">
                <a href="#" class="dropdown-toggle" data-toggle="dropdown" role="button" aria-haspopup="true" aria-expanded="false">Plots <span class="caret"></span></a>
                <ul class="dropdown-menu">
                 <li><a href="visualizations/temp.html">Max Temperature</a></li>
                  <li><a href="visualizations/humidity.html">Humidity</a></li>
                  <li><a href="visualizations/cloudiness.html">Cloudiness</a></li>
                  <li><a href="visualizations/wind.html">Wind Speed</a></li>
                </ul>
              </li>
              <li><a href="comparison.html">Comparison</a></li>
              <li><a href="data.html">Data</a></li>
            </ul>
          </div><!-- /.navbar-collapse -->
        </div>
      </div><!-- /.container-fluid -->
    </nav>
    <!-- End of navbar -->

    <!-- Start of container -->
    <div class="container">
      <article class="description-content row">
        <div class="col-xs-12">
          <h1 class="description-header">Data</h1>
          <hr class="description-hr"/>
          <p class="description-text">The following table includes all of the data used for plotting during this project.</p>
          <div class="table-responsive">
            <table class="table table-striped table-hover">
              <thead>
                <tr style="text-align: right;">
                  <th>City_ID</th>
                  <th>City</th>
                  <th>Cloudiness</th>
                  <th>Country</th>
                  <th>Date</th>
                  <th>Humidity</th>
                  <th>Lat</th>
                  <th>Lng</th>
                  <th>Max Temp</th>
                  <th>Wind Speed</th>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <td>0</td>
                  <td>jacareacanga</td>
                  <td>0</td>
                  <td>BR</td>
                  <td>1528902000</td>
                  <td>62</td>
                  <td>-6.22</td>
                  <td>-57.76</td>
                  <td>89.60</td>
                  <td>6.93</td>
                </tr>
                <tr>
                  <td>1</td>
                  <td>kaitangata</td>
                  <td>100</td>
                  <td>NZ</td>
                  <td>1528905304</td>
                  <td>94</td>
                  <td>-46.28</td>
                  <td>169.85</td>
                  <td>42.61</td>
                  <td>5.64</td>
                </tr>
                <tr>
                  <td>2</td>
                  <td>goulburn</td>
                  <td>20</td>
                  <td>AU</td>
                  <td>1528905078</td>
                  <td>91</td>
                  <td>-34.75</td>
                  <td>149.72</td>
                  <td>44.32</td>
                  <td>10.11</td>
                </tr>
                <tr>
                  <td>3</td>
                  <td>lata</td>
                  <td>76</td>
                  <td>IN</td>
                  <td>1528905305</td>
                  <td>89</td>
                  <td>30.78</td>
                  <td>78.62</td>
                  <td>59.89</td>
                  <td>0.94</td>
                </tr>
                <tr>
                  <td>4</td>
                  <td>chokurdakh</td>
                  <td>0</td>
                  <td>RU</td>
                  <td>1528905306</td>
                  <td>88</td>
                  <td>70.62</td>
                  <td>147.90</td>
                  <td>32.17</td>
                  <td>2.95</td>
                </tr>
                <tr>
                  <td>5</td>
                  <td>martyush</td>
                  <td>92</td>
                  <td>RU</td>
                  <td>1528905306</td>
                  <td>94</td>
                  <td>56.40</td>
                  <td>61.89</td>
                  <td>55.03</td>
                  <td>9.33</td>
                </tr>
                <tr>
                  <td>6</td>
                  <td>hobart</td>
                  <td>20</td>
                  <td>AU</td>
                  <td>1528902000</td>
                  <td>87</td>
                  <td>-42.88</td>
                  <td>147.33</td>
                  <td>44.60</td>
                  <td>8.05</td>
                </tr>
                <tr>
                  <td>7</td>
                  <td>broken hill</td>
                  <td>0</td>
                  <td>AU</td>
                  <td>1528905311</td>
                  <td>88</td>
                  <td>-31.97</td>
                  <td>141.45</td>
                  <td>44.50</td>
                  <td>7.31</td>
                </tr>
                <tr>
                  <td>8</td>
                  <td>harnosand</td>
                  <td>0</td>
                  <td>SE</td>
                  <td>1528903200</td>
                  <td>44</td>
                  <td>62.63</td>
                  <td>17.94</td>
                  <td>60.80</td>
                  <td>13.87</td>
                </tr>
                <tr>
                  <td>9</td>
                  <td>tuatapere</td>
                  <td>0</td>
                  <td>NZ</td>
                  <td>1528905312</td>
                  <td>100</td>
                  <td>-46.13</td>
                  <td>167.69</td>
                  <td>38.92</td>
                  <td>3.40</td>
                </tr>
                <tr>
                  <td>10</td>
                  <td>puerto ayora</td>
                  <td>90</td>
                  <td>EC</td>
                  <td>1528902000</td>
                  <td>69</td>
                  <td>-0.74</td>
                  <td>-90.35</td>
                  <td>77.00</td>
                  <td>13.87</td>
                </tr>
                <tr>
                  <td>11</td>
                  <td>havre-saint-pierre</td>
                  <td>75</td>
                  <td>CA</td>
                  <td>1528902000</td>
                  <td>58</td>
                  <td>50.23</td>
                  <td>-63.60</td>
                  <td>53.60</td>
                  <td>19.46</td>
                </tr>
                <tr>
                  <td>12</td>
                  <td>punta arenas</td>
                  <td>0</td>
                  <td>CL</td>
                  <td>1528902000</td>
                  <td>100</td>
                  <td>-53.16</td>
                  <td>-70.91</td>
                  <td>35.60</td>
                  <td>9.17</td>
                </tr>
                <tr>
                  <td>13</td>
                  <td>tasiilaq</td>
                  <td>75</td>
                  <td>GL</td>
                  <td>1528901400</td>
                  <td>60</td>
                  <td>65.61</td>
                  <td>-37.64</td>
                  <td>39.20</td>
                  <td>2.24</td>
                </tr>
                <tr>
                  <td>14</td>
                  <td>chapais</td>
                  <td>40</td>
                  <td>CA</td>
                  <td>1528902000</td>
                  <td>38</td>
                  <td>49.78</td>
                  <td>-74.86</td>
                  <td>59.00</td>
                  <td>10.29</td>
                </tr>
                <tr>
                  <td>15</td>
                  <td>avarua</td>
                  <td>40</td>
                  <td>CK</td>
                  <td>1528902000</td>
                  <td>56</td>
                  <td>-21.21</td>
                  <td>-159.78</td>
                  <td>73.40</td>
                  <td>10.29</td>
                </tr>
                <tr>
                  <td>16</td>
                  <td>hofn</td>
                  <td>75</td>
                  <td>IS</td>
                  <td>1528902000</td>
                  <td>87</td>
                  <td>64.25</td>
                  <td>-15.21</td>
                  <td>51.80</td>
                  <td>8.05</td>
                </tr>
                <tr>
                  <td>17</td>
                  <td>yukamenskoye</td>
                  <td>92</td>
                  <td>RU</td>
                  <td>1528905315</td>
                  <td>98</td>
                  <td>57.89</td>
                  <td>52.24</td>
                  <td>56.65</td>
                  <td>10.22</td>
                </tr>
                <tr>
                  <td>18</td>
                  <td>khandbari</td>
                  <td>80</td>
                  <td>NP</td>
                  <td>1528905315</td>
                  <td>67</td>
                  <td>27.38</td>
                  <td>87.21</td>
                  <td>44.59</td>
                  <td>1.39</td>
                </tr>
                <tr>
                  <td>19</td>
                  <td>bethel</td>
                  <td>1</td>
                  <td>US</td>
                  <td>1528901580</td>
                  <td>93</td>
                  <td>60.79</td>
                  <td>-161.76</td>
                  <td>44.60</td>
                  <td>8.05</td>
                </tr>
                <tr>
                  <td>20</td>
                  <td>ushuaia</td>
                  <td>75</td>
                  <td>AR</td>
                  <td>1528902000</td>
                  <td>64</td>
                  <td>-54.81</td>
                  <td>-68.31</td>
                  <td>41.00</td>
                  <td>3.36</td>
                </tr>
                <tr>
                  <td>21</td>
                  <td>east london</td>
                  <td>0</td>
                  <td>ZA</td>
                  <td>1528902000</td>
                  <td>37</td>
                  <td>-33.02</td>
                  <td>27.91</td>
                  <td>69.80</td>
                  <td>5.82</td>
                </tr>
                <tr>
                  <td>22</td>
                  <td>bluff</td>
                  <td>76</td>
                  <td>AU</td>
                  <td>1528905321</td>
                  <td>76</td>
                  <td>-23.58</td>
                  <td>149.07</td>
                  <td>61.96</td>
                  <td>4.74</td>
                </tr>
                <tr>
                  <td>23</td>
                  <td>mount isa</td>
                  <td>75</td>
                  <td>AU</td>
                  <td>1528902000</td>
                  <td>100</td>
                  <td>-20.73</td>
                  <td>139.49</td>
                  <td>64.40</td>
                  <td>3.29</td>
                </tr>
                <tr>
                  <td>24</td>
                  <td>pevek</td>
                  <td>0</td>
                  <td>RU</td>
                  <td>1528905321</td>
                  <td>71</td>
                  <td>69.70</td>
                  <td>170.27</td>
                  <td>36.94</td>
                  <td>6.98</td>
                </tr>
                <tr>
                  <td>25</td>
                  <td>gao</td>
                  <td>24</td>
                  <td>ML</td>
                  <td>1528905321</td>
                  <td>16</td>
                  <td>16.28</td>
                  <td>-0.04</td>
                  <td>110.02</td>
                  <td>4.97</td>
                </tr>
                <tr>
                  <td>26</td>
                  <td>cabo san lucas</td>
                  <td>75</td>
                  <td>MX</td>
                  <td>1528901160</td>
                  <td>74</td>
                  <td>22.89</td>
                  <td>-109.91</td>
                  <td>84.20</td>
                  <td>10.29</td>
                </tr>
                <tr>
                  <td>27</td>
                  <td>sao filipe</td>
                  <td>0</td>
                  <td>CV</td>
                  <td>1528905323</td>
                  <td>88</td>
                  <td>14.90</td>
                  <td>-24.50</td>
                  <td>75.73</td>
                  <td>13.02</td>
                </tr>
                <tr>
                  <td>28</td>
                  <td>tiksi</td>
                  <td>44</td>
                  <td>RU</td>
                  <td>1528905298</td>
                  <td>58</td>
                  <td>71.64</td>
                  <td>128.87</td>
                  <td>57.73</td>
                  <td>10.11</td>
                </tr>
                <tr>
                  <td>29</td>
                  <td>busselton</td>
                  <td>92</td>
                  <td>AU</td>
                  <td>1528905323</td>
                  <td>100</td>
                  <td>-33.64</td>
                  <td>115.35</td>
                  <td>60.43</td>
                  <td>10.56</td>
                </tr>
                <tr>
                  <td>30</td>
                  <td>alofi</td>
                  <td>76</td>
                  <td>NU</td>
                  <td>1528902000</td>
                  <td>88</td>
                  <td>-19.06</td>
                  <td>-169.92</td>
                  <td>71.60</td>
                  <td>3.36</td>
                </tr>
                <tr>
                  <td>31</td>
                  <td>ola</td>
                  <td>75</td>
                  <td>RU</td>
                  <td>1528902000</td>
                  <td>100</td>
                  <td>59.58</td>
                  <td>151.30</td>
                  <td>42.80</td>
                  <td>7.76</td>
                </tr>
                <tr>
                  <td>32</td>
                  <td>atar</td>
                  <td>20</td>
                  <td>MR</td>
                  <td>1528902000</td>
                  <td>19</td>
                  <td>20.52</td>
                  <td>-13.05</td>
                  <td>91.40</td>
                  <td>9.17</td>
                </tr>
                <tr>
                  <td>33</td>
                  <td>rikitea</td>
                  <td>0</td>
                  <td>PF</td>
                  <td>1528905325</td>
                  <td>100</td>
                  <td>-23.12</td>
                  <td>-134.97</td>
                  <td>73.57</td>
                  <td>8.66</td>
                </tr>
                <tr>
                  <td>34</td>
                  <td>hermanus</td>
                  <td>0</td>
                  <td>ZA</td>
                  <td>1528905325</td>
                  <td>24</td>
                  <td>-34.42</td>
                  <td>19.24</td>
                  <td>77.17</td>
                  <td>8.66</td>
                </tr>
                <tr>
                  <td>35</td>
                  <td>ponta delgada</td>
                  <td>75</td>
                  <td>PT</td>
                  <td>1528903800</td>
                  <td>88</td>
                  <td>37.73</td>
                  <td>-25.67</td>
                  <td>71.60</td>
                  <td>12.75</td>
                </tr>
                <tr>
                  <td>36</td>
                  <td>bambari</td>
                  <td>24</td>
                  <td>CF</td>
                  <td>1528905326</td>
                  <td>84</td>
                  <td>5.77</td>
                  <td>20.68</td>
                  <td>81.85</td>
                  <td>7.65</td>
                </tr>
                <tr>
                  <td>37</td>
                  <td>cap malheureux</td>
                  <td>75</td>
                  <td>MU</td>
                  <td>1528902000</td>
                  <td>69</td>
                  <td>-19.98</td>
                  <td>57.61</td>
                  <td>75.20</td>
                  <td>14.99</td>
                </tr>
                <tr>
                  <td>38</td>
                  <td>puerto escondido</td>
                  <td>75</td>
                  <td>MX</td>
                  <td>1528901100</td>
                  <td>65</td>
                  <td>15.86</td>
                  <td>-97.07</td>
                  <td>80.60</td>
                  <td>3.36</td>
                </tr>
                <tr>
                  <td>39</td>
                  <td>qaanaaq</td>
                  <td>32</td>
                  <td>GL</td>
                  <td>1528905330</td>
                  <td>100</td>
                  <td>77.48</td>
                  <td>-69.36</td>
                  <td>31.45</td>
                  <td>6.31</td>
                </tr>
                <tr>
                  <td>40</td>
                  <td>new norfolk</td>
                  <td>20</td>
                  <td>AU</td>
                  <td>1528902000</td>
                  <td>87</td>
                  <td>-42.78</td>
                  <td>147.06</td>
                  <td>44.60</td>
                  <td>8.05</td>
                </tr>
                <tr>
                  <td>41</td>
                  <td>najran</td>
                  <td>40</td>
                  <td>SA</td>
                  <td>1528902000</td>
                  <td>13</td>
                  <td>17.54</td>
                  <td>44.22</td>
                  <td>98.60</td>
                  <td>11.41</td>
                </tr>
                <tr>
                  <td>42</td>
                  <td>isla mujeres</td>
                  <td>90</td>
                  <td>MX</td>
                  <td>1528904340</td>
                  <td>100</td>
                  <td>21.23</td>
                  <td>-86.73</td>
                  <td>75.20</td>
                  <td>16.11</td>
                </tr>
                <tr>
                  <td>43</td>
                  <td>mar del plata</td>
                  <td>0</td>
                  <td>AR</td>
                  <td>1528905297</td>
                  <td>100</td>
                  <td>-46.43</td>
                  <td>-67.52</td>
                  <td>32.53</td>
                  <td>7.31</td>
                </tr>
                <tr>
                  <td>44</td>
                  <td>provideniya</td>
                  <td>0</td>
                  <td>RU</td>
                  <td>1528905332</td>
                  <td>91</td>
                  <td>64.42</td>
                  <td>-173.23</td>
                  <td>40.63</td>
                  <td>10.78</td>
                </tr>
                <tr>
                  <td>45</td>
                  <td>jamestown</td>
                  <td>12</td>
                  <td>AU</td>
                  <td>1528905333</td>
                  <td>88</td>
                  <td>-33.21</td>
                  <td>138.60</td>
                  <td>43.15</td>
                  <td>10.89</td>
                </tr>
                <tr>
                  <td>46</td>
                  <td>medicine hat</td>
                  <td>20</td>
                  <td>CA</td>
                  <td>1528902000</td>
                  <td>34</td>
                  <td>50.04</td>
                  <td>-110.68</td>
                  <td>66.20</td>
                  <td>14.99</td>
                </tr>
                <tr>
                  <td>47</td>
                  <td>katsuura</td>
                  <td>8</td>
                  <td>JP</td>
                  <td>1528905334</td>
                  <td>88</td>
                  <td>33.93</td>
                  <td>134.50</td>
                  <td>62.05</td>
                  <td>7.54</td>
                </tr>
                <tr>
                  <td>48</td>
                  <td>aklavik</td>
                  <td>20</td>
                  <td>CA</td>
                  <td>1528902000</td>
                  <td>53</td>
                  <td>68.22</td>
                  <td>-135.01</td>
                  <td>51.80</td>
                  <td>11.41</td>
                </tr>
                <tr>
                  <td>49</td>
                  <td>tuktoyaktuk</td>
                  <td>20</td>
                  <td>CA</td>
                  <td>1528902000</td>
                  <td>61</td>
                  <td>69.44</td>
                  <td>-133.03</td>
                  <td>46.40</td>
                  <td>6.93</td>
                </tr>
                <tr>
                  <td>50</td>
                  <td>kapaa</td>
                  <td>90</td>
                  <td>US</td>
                  <td>1528901760</td>
                  <td>88</td>
                  <td>22.08</td>
                  <td>-159.32</td>
                  <td>75.20</td>
                  <td>14.99</td>
                </tr>
                <tr>
                  <td>51</td>
                  <td>mildura</td>
                  <td>0</td>
                  <td>AU</td>
                  <td>1528905300</td>
                  <td>92</td>
                  <td>-34.18</td>
                  <td>142.16</td>
                  <td>45.67</td>
                  <td>9.66</td>
                </tr>
                <tr>
                  <td>52</td>
                  <td>souillac</td>
                  <td>75</td>
                  <td>FR</td>
                  <td>1528903800</td>
                  <td>49</td>
                  <td>45.60</td>
                  <td>-0.60</td>
                  <td>73.40</td>
                  <td>10.29</td>
                </tr>
                <tr>
                  <td>53</td>
                  <td>lorengau</td>
                  <td>100</td>
                  <td>PG</td>
                  <td>1528905336</td>
                  <td>100</td>
                  <td>-2.02</td>
                  <td>147.27</td>
                  <td>80.59</td>
                  <td>3.85</td>
                </tr>
                <tr>
                  <td>54</td>
                  <td>praia</td>
                  <td>20</td>
                  <td>BR</td>
                  <td>1528902000</td>
                  <td>47</td>
                  <td>-20.25</td>
                  <td>-43.81</td>
                  <td>82.40</td>
                  <td>3.36</td>
                </tr>
                <tr>
                  <td>55</td>
                  <td>port alfred</td>
                  <td>0</td>
                  <td>ZA</td>
                  <td>1528905338</td>
                  <td>50</td>
                  <td>-33.59</td>
                  <td>26.89</td>
                  <td>76.54</td>
                  <td>7.20</td>
                </tr>
                <tr>
                  <td>56</td>
                  <td>barranca</td>
                  <td>0</td>
                  <td>PE</td>
                  <td>1528905339</td>
                  <td>98</td>
                  <td>-10.75</td>
                  <td>-77.76</td>
                  <td>61.87</td>
                  <td>9.89</td>
                </tr>
                <tr>
                  <td>57</td>
                  <td>nome</td>
                  <td>40</td>
                  <td>US</td>
                  <td>1528902900</td>
                  <td>70</td>
                  <td>30.04</td>
                  <td>-94.42</td>
                  <td>87.80</td>
                  <td>3.36</td>
                </tr>
                <tr>
                  <td>58</td>
                  <td>matay</td>
                  <td>0</td>
                  <td>EG</td>
                  <td>1528905339</td>
                  <td>23</td>
                  <td>28.42</td>
                  <td>30.79</td>
                  <td>97.69</td>
                  <td>6.98</td>
                </tr>
                <tr>
                  <td>59</td>
                  <td>saskylakh</td>
                  <td>48</td>
                  <td>RU</td>
                  <td>1528905339</td>
                  <td>55</td>
                  <td>71.97</td>
                  <td>114.09</td>
                  <td>59.53</td>
                  <td>5.86</td>
                </tr>
                <tr>
                  <td>60</td>
                  <td>itarema</td>
                  <td>0</td>
                  <td>BR</td>
                  <td>1528905340</td>
                  <td>61</td>
                  <td>-2.92</td>
                  <td>-39.92</td>
                  <td>88.33</td>
                  <td>12.57</td>
                </tr>
                <tr>
                  <td>61</td>
                  <td>butaritari</td>
                  <td>56</td>
                  <td>KI</td>
                  <td>1528905340</td>
                  <td>100</td>
                  <td>3.07</td>
                  <td>172.79</td>
                  <td>81.13</td>
                  <td>7.31</td>
                </tr>
                <tr>
                  <td>62</td>
                  <td>peniche</td>
                  <td>20</td>
                  <td>PT</td>
                  <td>1528903800</td>
                  <td>64</td>
                  <td>39.36</td>
                  <td>-9.38</td>
                  <td>75.20</td>
                  <td>12.75</td>
                </tr>
                <tr>
                  <td>63</td>
                  <td>beloha</td>
                  <td>0</td>
                  <td>MG</td>
                  <td>1528905340</td>
                  <td>57</td>
                  <td>-25.17</td>
                  <td>45.06</td>
                  <td>71.95</td>
                  <td>16.37</td>
                </tr>
                <tr>
                  <td>64</td>
                  <td>anadyr</td>
                  <td>0</td>
                  <td>RU</td>
                  <td>1528902000</td>
                  <td>57</td>
                  <td>64.73</td>
                  <td>177.51</td>
                  <td>48.20</td>
                  <td>4.47</td>
                </tr>
                <tr>
                  <td>65</td>
                  <td>luderitz</td>
                  <td>12</td>
                  <td>NaN</td>
                  <td>1528905342</td>
                  <td>64</td>
                  <td>-26.65</td>
                  <td>15.16</td>
                  <td>64.03</td>
                  <td>17.38</td>
                </tr>
                <tr>
                  <td>66</td>
                  <td>rochester</td>
                  <td>1</td>
                  <td>US</td>
                  <td>1528902960</td>
                  <td>37</td>
                  <td>44.02</td>
                  <td>-92.46</td>
                  <td>73.40</td>
                  <td>6.93</td>
                </tr>
                <tr>
                  <td>67</td>
                  <td>bosaso</td>
                  <td>0</td>
                  <td>SO</td>
                  <td>1528905347</td>
                  <td>86</td>
                  <td>11.28</td>
                  <td>49.18</td>
                  <td>89.77</td>
                  <td>3.96</td>
                </tr>
                <tr>
                  <td>68</td>
                  <td>faanui</td>
                  <td>0</td>
                  <td>PF</td>
                  <td>1528905347</td>
                  <td>100</td>
                  <td>-16.48</td>
                  <td>-151.75</td>
                  <td>79.96</td>
                  <td>11.79</td>
                </tr>
                <tr>
                  <td>69</td>
                  <td>grindavik</td>
                  <td>75</td>
                  <td>IS</td>
                  <td>1528902000</td>
                  <td>70</td>
                  <td>63.84</td>
                  <td>-22.43</td>
                  <td>48.20</td>
                  <td>5.82</td>
                </tr>
                <tr>
                  <td>70</td>
                  <td>margate</td>
                  <td>20</td>
                  <td>AU</td>
                  <td>1528902000</td>
                  <td>87</td>
                  <td>-43.03</td>
                  <td>147.26</td>
                  <td>44.60</td>
                  <td>8.05</td>
                </tr>
                <tr>
                  <td>71</td>
                  <td>marsh harbour</td>
                  <td>88</td>
                  <td>BS</td>
                  <td>1528905349</td>
                  <td>95</td>
                  <td>26.54</td>
                  <td>-77.06</td>
                  <td>82.39</td>
                  <td>10.00</td>
                </tr>
                <tr>
                  <td>72</td>
                  <td>comodoro rivadavia</td>
                  <td>40</td>
                  <td>AR</td>
                  <td>1528902000</td>
                  <td>60</td>
                  <td>-45.87</td>
                  <td>-67.48</td>
                  <td>42.80</td>
                  <td>9.17</td>
                </tr>
                <tr>
                  <td>73</td>
                  <td>upernavik</td>
                  <td>92</td>
                  <td>GL</td>
                  <td>1528905350</td>
                  <td>100</td>
                  <td>72.79</td>
                  <td>-56.15</td>
                  <td>29.29</td>
                  <td>3.74</td>
                </tr>
                <tr>
                  <td>74</td>
                  <td>uige</td>
                  <td>0</td>
                  <td>AO</td>
                  <td>1528905350</td>
                  <td>29</td>
                  <td>-7.61</td>
                  <td>15.06</td>
                  <td>86.80</td>
                  <td>3.18</td>
                </tr>
                <tr>
                  <td>75</td>
                  <td>bredasdorp</td>
                  <td>0</td>
                  <td>ZA</td>
                  <td>1528902000</td>
                  <td>23</td>
                  <td>-34.53</td>
                  <td>20.04</td>
                  <td>82.40</td>
                  <td>5.82</td>
                </tr>
                <tr>
                  <td>76</td>
                  <td>bodden town</td>
                  <td>40</td>
                  <td>KY</td>
                  <td>1528902000</td>
                  <td>78</td>
                  <td>19.28</td>
                  <td>-81.25</td>
                  <td>80.60</td>
                  <td>16.11</td>
                </tr>
                <tr>
                  <td>77</td>
                  <td>guerrero negro</td>
                  <td>44</td>
                  <td>MX</td>
                  <td>1528905350</td>
                  <td>88</td>
                  <td>27.97</td>
                  <td>-114.04</td>
                  <td>63.85</td>
                  <td>3.74</td>
                </tr>
                <tr>
                  <td>78</td>
                  <td>bilma</td>
                  <td>0</td>
                  <td>NE</td>
                  <td>1528905351</td>
                  <td>12</td>
                  <td>18.69</td>
                  <td>12.92</td>
                  <td>110.47</td>
                  <td>4.63</td>
                </tr>
                <tr>
                  <td>79</td>
                  <td>carnarvon</td>
                  <td>0</td>
                  <td>ZA</td>
                  <td>1528905351</td>
                  <td>30</td>
                  <td>-30.97</td>
                  <td>22.13</td>
                  <td>60.43</td>
                  <td>14.25</td>
                </tr>
                <tr>
                  <td>80</td>
                  <td>ponta do sol</td>
                  <td>12</td>
                  <td>BR</td>
                  <td>1528905352</td>
                  <td>72</td>
                  <td>-20.63</td>
                  <td>-46.00</td>
                  <td>78.25</td>
                  <td>3.96</td>
                </tr>
                <tr>
                  <td>81</td>
                  <td>vila franca do campo</td>
                  <td>75</td>
                  <td>PT</td>
                  <td>1528903800</td>
                  <td>88</td>
                  <td>37.72</td>
                  <td>-25.43</td>
                  <td>71.60</td>
                  <td>12.75</td>
                </tr>
                <tr>
                  <td>82</td>
                  <td>puerto del rosario</td>
                  <td>20</td>
                  <td>ES</td>
                  <td>1528903800</td>
                  <td>60</td>
                  <td>28.50</td>
                  <td>-13.86</td>
                  <td>73.40</td>
                  <td>17.22</td>
                </tr>
                <tr>
                  <td>83</td>
                  <td>sitka</td>
                  <td>20</td>
                  <td>US</td>
                  <td>1528905353</td>
                  <td>92</td>
                  <td>37.17</td>
                  <td>-99.65</td>
                  <td>74.02</td>
                  <td>5.97</td>
                </tr>
                <tr>
                  <td>84</td>
                  <td>camacha</td>
                  <td>75</td>
                  <td>PT</td>
                  <td>1528903800</td>
                  <td>72</td>
                  <td>33.08</td>
                  <td>-16.33</td>
                  <td>68.00</td>
                  <td>16.11</td>
                </tr>
                <tr>
                  <td>85</td>
                  <td>saint-philippe</td>
                  <td>1</td>
                  <td>CA</td>
                  <td>1528902900</td>
                  <td>54</td>
                  <td>45.36</td>
                  <td>-73.48</td>
                  <td>78.80</td>
                  <td>11.41</td>
                </tr>
                <tr>
                  <td>86</td>
                  <td>port blair</td>
                  <td>92</td>
                  <td>IN</td>
                  <td>1528905357</td>
                  <td>97</td>
                  <td>11.67</td>
                  <td>92.75</td>
                  <td>84.37</td>
                  <td>25.10</td>
                </tr>
                <tr>
                  <td>87</td>
                  <td>albany</td>
                  <td>90</td>
                  <td>US</td>
                  <td>1528903860</td>
                  <td>68</td>
                  <td>42.65</td>
                  <td>-73.75</td>
                  <td>69.80</td>
                  <td>3.36</td>
                </tr>
                <tr>
                  <td>88</td>
                  <td>barrow</td>
                  <td>88</td>
                  <td>AR</td>
                  <td>1528905182</td>
                  <td>72</td>
                  <td>-38.31</td>
                  <td>-60.23</td>
                  <td>50.26</td>
                  <td>8.21</td>
                </tr>
                <tr>
                  <td>89</td>
                  <td>qorveh</td>
                  <td>92</td>
                  <td>IR</td>
                  <td>1528905357</td>
                  <td>22</td>
                  <td>35.17</td>
                  <td>47.80</td>
                  <td>76.72</td>
                  <td>3.18</td>
                </tr>
                <tr>
                  <td>90</td>
                  <td>san jeronimo</td>
                  <td>90</td>
                  <td>PE</td>
                  <td>1528902000</td>
                  <td>81</td>
                  <td>-13.65</td>
                  <td>-73.37</td>
                  <td>46.40</td>
                  <td>2.39</td>
                </tr>
                <tr>
                  <td>91</td>
                  <td>mataura</td>
                  <td>24</td>
                  <td>NZ</td>
                  <td>1528905299</td>
                  <td>79</td>
                  <td>-46.19</td>
                  <td>168.86</td>
                  <td>25.69</td>
                  <td>3.18</td>
                </tr>
                <tr>
                  <td>92</td>
                  <td>buala</td>
                  <td>64</td>
                  <td>SB</td>
                  <td>1528905359</td>
                  <td>100</td>
                  <td>-8.15</td>
                  <td>159.59</td>
                  <td>78.70</td>
                  <td>4.18</td>
                </tr>
                <tr>
                  <td>93</td>
                  <td>eyl</td>
                  <td>20</td>
                  <td>SO</td>
                  <td>1528905359</td>
                  <td>57</td>
                  <td>7.98</td>
                  <td>49.82</td>
                  <td>86.62</td>
                  <td>22.41</td>
                </tr>
                <tr>
                  <td>94</td>
                  <td>abu dhabi</td>
                  <td>0</td>
                  <td>AE</td>
                  <td>1528902000</td>
                  <td>29</td>
                  <td>24.47</td>
                  <td>54.37</td>
                  <td>98.60</td>
                  <td>16.11</td>
                </tr>
                <tr>
                  <td>95</td>
                  <td>tahe</td>
                  <td>92</td>
                  <td>CN</td>
                  <td>1528905359</td>
                  <td>98</td>
                  <td>52.34</td>
                  <td>124.71</td>
                  <td>51.43</td>
                  <td>2.17</td>
                </tr>
                <tr>
                  <td>96</td>
                  <td>chuy</td>
                  <td>80</td>
                  <td>UY</td>
                  <td>1528905099</td>
                  <td>93</td>
                  <td>-33.69</td>
                  <td>-53.46</td>
                  <td>52.87</td>
                  <td>28.90</td>
                </tr>
                <tr>
                  <td>97</td>
                  <td>dzerzhinskoye</td>
                  <td>8</td>
                  <td>RU</td>
                  <td>1528905360</td>
                  <td>69</td>
                  <td>56.84</td>
                  <td>95.22</td>
                  <td>65.11</td>
                  <td>3.85</td>
                </tr>
                <tr>
                  <td>98</td>
                  <td>vanavara</td>
                  <td>0</td>
                  <td>RU</td>
                  <td>1528905360</td>
                  <td>50</td>
                  <td>60.35</td>
                  <td>102.28</td>
                  <td>64.21</td>
                  <td>5.64</td>
                </tr>
                <tr>
                  <td>99</td>
                  <td>muros</td>
                  <td>40</td>
                  <td>ES</td>
                  <td>1528903800</td>
                  <td>72</td>
                  <td>42.77</td>
                  <td>-9.06</td>
                  <td>66.20</td>
                  <td>10.29</td>
                </tr>
                <tr>
                  <td>100</td>
                  <td>auchel</td>
                  <td>0</td>
                  <td>FR</td>
                  <td>1528903800</td>
                  <td>49</td>
                  <td>50.51</td>
                  <td>2.47</td>
                  <td>68.00</td>
                  <td>3.36</td>
                </tr>
                <tr>
                  <td>101</td>
                  <td>bubaque</td>
                  <td>40</td>
                  <td>GW</td>
                  <td>1528902000</td>
                  <td>55</td>
                  <td>11.28</td>
                  <td>-15.83</td>
                  <td>91.40</td>
                  <td>11.41</td>
                </tr>
                <tr>
                  <td>102</td>
                  <td>khatanga</td>
                  <td>8</td>
                  <td>RU</td>
                  <td>1528905361</td>
                  <td>65</td>
                  <td>71.98</td>
                  <td>102.47</td>
                  <td>60.97</td>
                  <td>4.63</td>
                </tr>
                <tr>
                  <td>103</td>
                  <td>los banos</td>
                  <td>1</td>
                  <td>US</td>
                  <td>1528904100</td>
                  <td>67</td>
                  <td>37.06</td>
                  <td>-120.85</td>
                  <td>75.20</td>
                  <td>4.74</td>
                </tr>
                <tr>
                  <td>104</td>
                  <td>labuhan</td>
                  <td>12</td>
                  <td>ID</td>
                  <td>1528905361</td>
                  <td>95</td>
                  <td>-2.54</td>
                  <td>115.51</td>
                  <td>72.94</td>
                  <td>1.83</td>
                </tr>
                <tr>
                  <td>105</td>
                  <td>saint-paul</td>
                  <td>75</td>
                  <td>FR</td>
                  <td>1528903800</td>
                  <td>56</td>
                  <td>45.22</td>
                  <td>1.90</td>
                  <td>68.00</td>
                  <td>14.99</td>
                </tr>
                <tr>
                  <td>106</td>
                  <td>petatlan</td>
                  <td>90</td>
                  <td>MX</td>
                  <td>1528901220</td>
                  <td>74</td>
                  <td>17.52</td>
                  <td>-101.27</td>
                  <td>84.20</td>
                  <td>1.83</td>
                </tr>
                <tr>
                  <td>107</td>
                  <td>baykit</td>
                  <td>36</td>
                  <td>RU</td>
                  <td>1528905366</td>
                  <td>68</td>
                  <td>61.68</td>
                  <td>96.39</td>
                  <td>63.94</td>
                  <td>4.29</td>
                </tr>
                <tr>
                  <td>108</td>
                  <td>dalby</td>
                  <td>75</td>
                  <td>AU</td>
                  <td>1528902000</td>
                  <td>93</td>
                  <td>-27.18</td>
                  <td>151.26</td>
                  <td>53.60</td>
                  <td>2.24</td>
                </tr>
                <tr>
                  <td>109</td>
                  <td>yellowknife</td>
                  <td>90</td>
                  <td>CA</td>
                  <td>1528902540</td>
                  <td>93</td>
                  <td>62.45</td>
                  <td>-114.38</td>
                  <td>46.40</td>
                  <td>8.05</td>
                </tr>
                <tr>
                  <td>110</td>
                  <td>hilo</td>
                  <td>75</td>
                  <td>US</td>
                  <td>1528901580</td>
                  <td>88</td>
                  <td>19.71</td>
                  <td>-155.08</td>
                  <td>66.20</td>
                  <td>5.82</td>
                </tr>
                <tr>
                  <td>111</td>
                  <td>turukhansk</td>
                  <td>36</td>
                  <td>RU</td>
                  <td>1528905297</td>
                  <td>76</td>
                  <td>65.80</td>
                  <td>87.96</td>
                  <td>66.37</td>
                  <td>6.42</td>
                </tr>
                <tr>
                  <td>112</td>
                  <td>dingle</td>
                  <td>68</td>
                  <td>PH</td>
                  <td>1528905368</td>
                  <td>82</td>
                  <td>11.00</td>
                  <td>122.67</td>
                  <td>79.96</td>
                  <td>8.21</td>
                </tr>
                <tr>
                  <td>113</td>
                  <td>dillon</td>
                  <td>1</td>
                  <td>US</td>
                  <td>1528901580</td>
                  <td>44</td>
                  <td>45.22</td>
                  <td>-112.64</td>
                  <td>57.20</td>
                  <td>5.82</td>
                </tr>
                <tr>
                  <td>114</td>
                  <td>labytnangi</td>
                  <td>64</td>
                  <td>RU</td>
                  <td>1528905370</td>
                  <td>75</td>
                  <td>66.66</td>
                  <td>66.39</td>
                  <td>47.11</td>
                  <td>17.49</td>
                </tr>
                <tr>
                  <td>115</td>
                  <td>gigmoto</td>
                  <td>36</td>
                  <td>PH</td>
                  <td>1528905370</td>
                  <td>98</td>
                  <td>13.78</td>
                  <td>124.39</td>
                  <td>83.56</td>
                  <td>17.60</td>
                </tr>
                <tr>
                  <td>116</td>
                  <td>nouakchott</td>
                  <td>68</td>
                  <td>MR</td>
                  <td>1528905371</td>
                  <td>76</td>
                  <td>18.08</td>
                  <td>-15.98</td>
                  <td>76.72</td>
                  <td>1.39</td>
                </tr>
                <tr>
                  <td>117</td>
                  <td>rumoi</td>
                  <td>92</td>
                  <td>JP</td>
                  <td>1528905371</td>
                  <td>100</td>
                  <td>43.93</td>
                  <td>141.67</td>
                  <td>44.41</td>
                  <td>8.10</td>
                </tr>
                <tr>
                  <td>118</td>
                  <td>dikson</td>
                  <td>32</td>
                  <td>RU</td>
                  <td>1528905373</td>
                  <td>100</td>
                  <td>73.51</td>
                  <td>80.55</td>
                  <td>31.09</td>
                  <td>13.13</td>
                </tr>
                <tr>
                  <td>119</td>
                  <td>chinsali</td>
                  <td>0</td>
                  <td>ZM</td>
                  <td>1528905377</td>
                  <td>36</td>
                  <td>-10.55</td>
                  <td>32.07</td>
                  <td>73.39</td>
                  <td>9.22</td>
                </tr>
                <tr>
                  <td>120</td>
                  <td>georgetown</td>
                  <td>75</td>
                  <td>GY</td>
                  <td>1528902000</td>
                  <td>78</td>
                  <td>6.80</td>
                  <td>-58.16</td>
                  <td>82.40</td>
                  <td>9.17</td>
                </tr>
                <tr>
                  <td>121</td>
                  <td>tooele</td>
                  <td>1</td>
                  <td>US</td>
                  <td>1528902900</td>
                  <td>35</td>
                  <td>40.53</td>
                  <td>-112.30</td>
                  <td>73.40</td>
                  <td>9.17</td>
                </tr>
                <tr>
                  <td>122</td>
                  <td>nikolskoye</td>
                  <td>40</td>
                  <td>RU</td>
                  <td>1528902000</td>
                  <td>41</td>
                  <td>59.70</td>
                  <td>30.79</td>
                  <td>60.80</td>
                  <td>4.47</td>
                </tr>
                <tr>
                  <td>123</td>
                  <td>bodo</td>
                  <td>80</td>
                  <td>CI</td>
                  <td>1528905379</td>
                  <td>66</td>
                  <td>5.91</td>
                  <td>-4.68</td>
                  <td>87.70</td>
                  <td>8.21</td>
                </tr>
                <tr>
                  <td>124</td>
                  <td>minador do negrao</td>
                  <td>32</td>
                  <td>BR</td>
                  <td>1528905379</td>
                  <td>80</td>
                  <td>-9.31</td>
                  <td>-36.86</td>
                  <td>76.81</td>
                  <td>13.24</td>
                </tr>
                <tr>
                  <td>125</td>
                  <td>sambava</td>
                  <td>88</td>
                  <td>MG</td>
                  <td>1528905379</td>
                  <td>100</td>
                  <td>-14.27</td>
                  <td>50.17</td>
                  <td>77.35</td>
                  <td>19.73</td>
                </tr>
                <tr>
                  <td>126</td>
                  <td>yerbogachen</td>
                  <td>0</td>
                  <td>RU</td>
                  <td>1528905380</td>
                  <td>44</td>
                  <td>61.28</td>
                  <td>108.01</td>
                  <td>64.93</td>
                  <td>7.43</td>
                </tr>
                <tr>
                  <td>127</td>
                  <td>kahului</td>
                  <td>1</td>
                  <td>US</td>
                  <td>1528901760</td>
                  <td>93</td>
                  <td>20.89</td>
                  <td>-156.47</td>
                  <td>66.20</td>
                  <td>3.36</td>
                </tr>
                <tr>
                  <td>128</td>
                  <td>clyde river</td>
                  <td>75</td>
                  <td>CA</td>
                  <td>1528902660</td>
                  <td>100</td>
                  <td>70.47</td>
                  <td>-68.59</td>
                  <td>35.60</td>
                  <td>21.92</td>
                </tr>
                <tr>
                  <td>129</td>
                  <td>ancud</td>
                  <td>20</td>
                  <td>CL</td>
                  <td>1528905381</td>
                  <td>90</td>
                  <td>-41.87</td>
                  <td>-73.83</td>
                  <td>39.10</td>
                  <td>2.73</td>
                </tr>
                <tr>
                  <td>130</td>
                  <td>beringovskiy</td>
                  <td>0</td>
                  <td>RU</td>
                  <td>1528905381</td>
                  <td>88</td>
                  <td>63.05</td>
                  <td>179.32</td>
                  <td>39.37</td>
                  <td>3.40</td>
                </tr>
                <tr>
                  <td>131</td>
                  <td>majene</td>
                  <td>32</td>
                  <td>ID</td>
                  <td>1528905382</td>
                  <td>100</td>
                  <td>-3.54</td>
                  <td>118.97</td>
                  <td>81.85</td>
                  <td>11.01</td>
                </tr>
                <tr>
                  <td>132</td>
                  <td>ahar</td>
                  <td>36</td>
                  <td>IR</td>
                  <td>1528905382</td>
                  <td>62</td>
                  <td>38.48</td>
                  <td>47.07</td>
                  <td>62.77</td>
                  <td>3.74</td>
                </tr>
                <tr>
                  <td>133</td>
                  <td>ilhabela</td>
                  <td>80</td>
                  <td>BR</td>
                  <td>1528905382</td>
                  <td>98</td>
                  <td>-23.78</td>
                  <td>-45.36</td>
                  <td>72.85</td>
                  <td>2.28</td>
                </tr>
                <tr>
                  <td>134</td>
                  <td>listvyagi</td>
                  <td>0</td>
                  <td>RU</td>
                  <td>1528905382</td>
                  <td>78</td>
                  <td>53.68</td>
                  <td>86.95</td>
                  <td>65.11</td>
                  <td>2.06</td>
                </tr>
                <tr>
                  <td>135</td>
                  <td>skjervoy</td>
                  <td>40</td>
                  <td>NO</td>
                  <td>1528903200</td>
                  <td>65</td>
                  <td>70.03</td>
                  <td>20.97</td>
                  <td>44.60</td>
                  <td>10.29</td>
                </tr>
                <tr>
                  <td>136</td>
                  <td>cape town</td>
                  <td>0</td>
                  <td>ZA</td>
                  <td>1528902000</td>
                  <td>35</td>
                  <td>-33.93</td>
                  <td>18.42</td>
                  <td>73.40</td>
                  <td>9.17</td>
                </tr>
                <tr>
                  <td>137</td>
                  <td>iqaluit</td>
                  <td>90</td>
                  <td>CA</td>
                  <td>1528902000</td>
                  <td>96</td>
                  <td>63.75</td>
                  <td>-68.52</td>
                  <td>35.60</td>
                  <td>20.80</td>
                </tr>
                <tr>
                  <td>138</td>
                  <td>fort-shevchenko</td>
                  <td>0</td>
                  <td>KZ</td>
                  <td>1528905387</td>
                  <td>59</td>
                  <td>44.51</td>
                  <td>50.26</td>
                  <td>74.20</td>
                  <td>3.62</td>
                </tr>
                <tr>
                  <td>139</td>
                  <td>severo-kurilsk</td>
                  <td>92</td>
                  <td>RU</td>
                  <td>1528905387</td>
                  <td>100</td>
                  <td>50.68</td>
                  <td>156.12</td>
                  <td>38.02</td>
                  <td>16.26</td>
                </tr>
                <tr>
                  <td>140</td>
                  <td>arraial do cabo</td>
                  <td>0</td>
                  <td>BR</td>
                  <td>1528905600</td>
                  <td>65</td>
                  <td>-22.97</td>
                  <td>-42.02</td>
                  <td>80.60</td>
                  <td>4.70</td>
                </tr>
                <tr>
                  <td>141</td>
                  <td>torbay</td>
                  <td>90</td>
                  <td>CA</td>
                  <td>1528903560</td>
                  <td>93</td>
                  <td>47.66</td>
                  <td>-52.73</td>
                  <td>50.00</td>
                  <td>19.46</td>
                </tr>
                <tr>
                  <td>142</td>
                  <td>ahipara</td>
                  <td>88</td>
                  <td>NZ</td>
                  <td>1528905388</td>
                  <td>91</td>
                  <td>-35.17</td>
                  <td>173.16</td>
                  <td>56.65</td>
                  <td>9.66</td>
                </tr>
                <tr>
                  <td>143</td>
                  <td>bandarbeyla</td>
                  <td>0</td>
                  <td>SO</td>
                  <td>1528905389</td>
                  <td>79</td>
                  <td>9.49</td>
                  <td>50.81</td>
                  <td>79.15</td>
                  <td>32.93</td>
                </tr>
                <tr>
                  <td>144</td>
                  <td>vuktyl</td>
                  <td>92</td>
                  <td>RU</td>
                  <td>1528905389</td>
                  <td>96</td>
                  <td>63.86</td>
                  <td>57.31</td>
                  <td>52.60</td>
                  <td>7.43</td>
                </tr>
                <tr>
                  <td>145</td>
                  <td>caravelas</td>
                  <td>0</td>
                  <td>BR</td>
                  <td>1528905390</td>
                  <td>98</td>
                  <td>-17.73</td>
                  <td>-39.27</td>
                  <td>77.62</td>
                  <td>10.45</td>
                </tr>
                <tr>
                  <td>146</td>
                  <td>waipawa</td>
                  <td>92</td>
                  <td>NZ</td>
                  <td>1528905390</td>
                  <td>94</td>
                  <td>-39.94</td>
                  <td>176.59</td>
                  <td>50.89</td>
                  <td>9.44</td>
                </tr>
                <tr>
                  <td>147</td>
                  <td>khomutovo</td>
                  <td>0</td>
                  <td>RU</td>
                  <td>1528905390</td>
                  <td>65</td>
                  <td>52.85</td>
                  <td>37.45</td>
                  <td>72.31</td>
                  <td>5.97</td>
                </tr>
                <tr>
                  <td>148</td>
                  <td>acajutla</td>
                  <td>40</td>
                  <td>SV</td>
                  <td>1528901400</td>
                  <td>79</td>
                  <td>13.59</td>
                  <td>-89.83</td>
                  <td>84.20</td>
                  <td>1.12</td>
                </tr>
                <tr>
                  <td>149</td>
                  <td>buritis</td>
                  <td>0</td>
                  <td>BR</td>
                  <td>1528905391</td>
                  <td>53</td>
                  <td>-15.62</td>
                  <td>-46.42</td>
                  <td>83.74</td>
                  <td>6.87</td>
                </tr>
                <tr>
                  <td>150</td>
                  <td>meulaboh</td>
                  <td>48</td>
                  <td>ID</td>
                  <td>1528905392</td>
                  <td>100</td>
                  <td>4.14</td>
                  <td>96.13</td>
                  <td>82.03</td>
                  <td>3.40</td>
                </tr>
                <tr>
                  <td>151</td>
                  <td>vaini</td>
                  <td>100</td>
                  <td>IN</td>
                  <td>1528905392</td>
                  <td>98</td>
                  <td>15.34</td>
                  <td>74.49</td>
                  <td>70.42</td>
                  <td>4.29</td>
                </tr>
                <tr>
                  <td>152</td>
                  <td>teya</td>
                  <td>75</td>
                  <td>MX</td>
                  <td>1528901400</td>
                  <td>66</td>
                  <td>21.05</td>
                  <td>-89.07</td>
                  <td>86.00</td>
                  <td>13.87</td>
                </tr>
                <tr>
                  <td>153</td>
                  <td>bambous virieux</td>
                  <td>75</td>
                  <td>MU</td>
                  <td>1528902000</td>
                  <td>69</td>
                  <td>-20.34</td>
                  <td>57.76</td>
                  <td>75.20</td>
                  <td>14.99</td>
                </tr>
                <tr>
                  <td>154</td>
                  <td>zaragoza</td>
                  <td>20</td>
                  <td>ES</td>
                  <td>1528903800</td>
                  <td>49</td>
                  <td>41.65</td>
                  <td>-0.88</td>
                  <td>77.00</td>
                  <td>28.86</td>
                </tr>
                <tr>
                  <td>155</td>
                  <td>thompson</td>
                  <td>75</td>
                  <td>CA</td>
                  <td>1528902600</td>
                  <td>76</td>
                  <td>55.74</td>
                  <td>-97.86</td>
                  <td>57.20</td>
                  <td>3.36</td>
                </tr>
                <tr>
                  <td>156</td>
                  <td>kodiak</td>
                  <td>1</td>
                  <td>US</td>
                  <td>1528901580</td>
                  <td>50</td>
                  <td>39.95</td>
                  <td>-94.76</td>
                  <td>75.20</td>
                  <td>13.87</td>
                </tr>
                <tr>
                  <td>157</td>
                  <td>nsanje</td>
                  <td>92</td>
                  <td>MZ</td>
                  <td>1528905397</td>
                  <td>84</td>
                  <td>-16.92</td>
                  <td>35.26</td>
                  <td>70.33</td>
                  <td>4.18</td>
                </tr>
                <tr>
                  <td>158</td>
                  <td>the pas</td>
                  <td>1</td>
                  <td>CA</td>
                  <td>1528902000</td>
                  <td>63</td>
                  <td>53.82</td>
                  <td>-101.24</td>
                  <td>60.80</td>
                  <td>10.29</td>
                </tr>
                <tr>
                  <td>159</td>
                  <td>masalli</td>
                  <td>12</td>
                  <td>KR</td>
                  <td>1528902000</td>
                  <td>77</td>
                  <td>34.80</td>
                  <td>126.66</td>
                  <td>68.00</td>
                  <td>9.17</td>
                </tr>
                <tr>
                  <td>160</td>
                  <td>talnakh</td>
                  <td>20</td>
                  <td>RU</td>
                  <td>1528905398</td>
                  <td>100</td>
                  <td>69.49</td>
                  <td>88.39</td>
                  <td>42.79</td>
                  <td>3.18</td>
                </tr>
                <tr>
                  <td>161</td>
                  <td>ilulissat</td>
                  <td>90</td>
                  <td>GL</td>
                  <td>1528901400</td>
                  <td>97</td>
                  <td>69.22</td>
                  <td>-51.10</td>
                  <td>32.00</td>
                  <td>4.70</td>
                </tr>
                <tr>
                  <td>162</td>
                  <td>vallenar</td>
                  <td>0</td>
                  <td>CL</td>
                  <td>1528905399</td>
                  <td>56</td>
                  <td>-28.58</td>
                  <td>-70.76</td>
                  <td>54.40</td>
                  <td>1.28</td>
                </tr>
                <tr>
                  <td>163</td>
                  <td>cap-aux-meules</td>
                  <td>40</td>
                  <td>CA</td>
                  <td>1528902000</td>
                  <td>62</td>
                  <td>47.38</td>
                  <td>-61.86</td>
                  <td>51.80</td>
                  <td>20.80</td>
                </tr>
                <tr>
                  <td>164</td>
                  <td>san quintin</td>
                  <td>90</td>
                  <td>PH</td>
                  <td>1528902000</td>
                  <td>100</td>
                  <td>17.54</td>
                  <td>120.52</td>
                  <td>77.00</td>
                  <td>13.87</td>
                </tr>
                <tr>
                  <td>165</td>
                  <td>victoria</td>
                  <td>75</td>
                  <td>BN</td>
                  <td>1528902000</td>
                  <td>94</td>
                  <td>5.28</td>
                  <td>115.24</td>
                  <td>80.60</td>
                  <td>1.12</td>
                </tr>
                <tr>
                  <td>166</td>
                  <td>okhotsk</td>
                  <td>12</td>
                  <td>RU</td>
                  <td>1528905400</td>
                  <td>100</td>
                  <td>59.36</td>
                  <td>143.24</td>
                  <td>38.02</td>
                  <td>2.17</td>
                </tr>
                <tr>
                  <td>167</td>
                  <td>bonavista</td>
                  <td>92</td>
                  <td>CA</td>
                  <td>1528905401</td>
                  <td>82</td>
                  <td>48.65</td>
                  <td>-53.11</td>
                  <td>46.57</td>
                  <td>22.97</td>
                </tr>
                <tr>
                  <td>168</td>
                  <td>manokwari</td>
                  <td>80</td>
                  <td>ID</td>
                  <td>1528905401</td>
                  <td>100</td>
                  <td>-0.87</td>
                  <td>134.08</td>
                  <td>78.07</td>
                  <td>8.10</td>
                </tr>
                <tr>
                  <td>169</td>
                  <td>lebu</td>
                  <td>92</td>
                  <td>ET</td>
                  <td>1528905404</td>
                  <td>100</td>
                  <td>8.96</td>
                  <td>38.73</td>
                  <td>55.30</td>
                  <td>0.72</td>
                </tr>
                <tr>
                  <td>170</td>
                  <td>qostanay</td>
                  <td>75</td>
                  <td>KZ</td>
                  <td>1528902000</td>
                  <td>54</td>
                  <td>53.17</td>
                  <td>63.58</td>
                  <td>59.00</td>
                  <td>6.71</td>
                </tr>
                <tr>
                  <td>171</td>
                  <td>victor harbor</td>
                  <td>75</td>
                  <td>AU</td>
                  <td>1528902000</td>
                  <td>82</td>
                  <td>-35.55</td>
                  <td>138.62</td>
                  <td>55.40</td>
                  <td>17.22</td>
                </tr>
                <tr>
                  <td>172</td>
                  <td>kamenka</td>
                  <td>12</td>
                  <td>RU</td>
                  <td>1528905405</td>
                  <td>98</td>
                  <td>53.19</td>
                  <td>44.05</td>
                  <td>61.60</td>
                  <td>9.44</td>
                </tr>
                <tr>
                  <td>173</td>
                  <td>cherskiy</td>
                  <td>8</td>
                  <td>RU</td>
                  <td>1528905405</td>
                  <td>48</td>
                  <td>68.75</td>
                  <td>161.30</td>
                  <td>55.21</td>
                  <td>3.18</td>
                </tr>
                <tr>
                  <td>174</td>
                  <td>kimbe</td>
                  <td>92</td>
                  <td>PG</td>
                  <td>1528905405</td>
                  <td>100</td>
                  <td>-5.56</td>
                  <td>150.15</td>
                  <td>78.43</td>
                  <td>6.64</td>
                </tr>
                <tr>
                  <td>175</td>
                  <td>guba</td>
                  <td>75</td>
                  <td>PH</td>
                  <td>1528902000</td>
                  <td>74</td>
                  <td>10.43</td>
                  <td>123.89</td>
                  <td>84.20</td>
                  <td>8.05</td>
                </tr>
                <tr>
                  <td>176</td>
                  <td>inuvik</td>
                  <td>40</td>
                  <td>CA</td>
                  <td>1528902000</td>
                  <td>53</td>
                  <td>68.36</td>
                  <td>-133.71</td>
                  <td>51.80</td>
                  <td>3.36</td>
                </tr>
                <tr>
                  <td>177</td>
                  <td>jiazi</td>
                  <td>20</td>
                  <td>CN</td>
                  <td>1528902000</td>
                  <td>78</td>
                  <td>19.61</td>
                  <td>110.49</td>
                  <td>82.40</td>
                  <td>4.47</td>
                </tr>
                <tr>
                  <td>178</td>
                  <td>namatanai</td>
                  <td>76</td>
                  <td>PG</td>
                  <td>1528905407</td>
                  <td>100</td>
                  <td>-3.66</td>
                  <td>152.44</td>
                  <td>78.07</td>
                  <td>11.68</td>
                </tr>
                <tr>
                  <td>179</td>
                  <td>port elizabeth</td>
                  <td>90</td>
                  <td>US</td>
                  <td>1528903500</td>
                  <td>83</td>
                  <td>39.31</td>
                  <td>-74.98</td>
                  <td>75.20</td>
                  <td>9.17</td>
                </tr>
                <tr>
                  <td>180</td>
                  <td>chilca</td>
                  <td>75</td>
                  <td>PE</td>
                  <td>1528903800</td>
                  <td>47</td>
                  <td>-13.22</td>
                  <td>-72.34</td>
                  <td>55.40</td>
                  <td>3.36</td>
                </tr>
                <tr>
                  <td>181</td>
                  <td>tual</td>
                  <td>68</td>
                  <td>ID</td>
                  <td>1528905408</td>
                  <td>100</td>
                  <td>-5.67</td>
                  <td>132.75</td>
                  <td>79.78</td>
                  <td>12.12</td>
                </tr>
                <tr>
                  <td>182</td>
                  <td>puerto colombia</td>
                  <td>40</td>
                  <td>CO</td>
                  <td>1528902000</td>
                  <td>74</td>
                  <td>10.99</td>
                  <td>-74.96</td>
                  <td>87.80</td>
                  <td>6.93</td>
                </tr>
                <tr>
                  <td>183</td>
                  <td>muzhi</td>
                  <td>0</td>
                  <td>RU</td>
                  <td>1528905409</td>
                  <td>63</td>
                  <td>65.40</td>
                  <td>64.70</td>
                  <td>55.57</td>
                  <td>10.67</td>
                </tr>
                <tr>
                  <td>184</td>
                  <td>tabuk</td>
                  <td>92</td>
                  <td>PH</td>
                  <td>1528905413</td>
                  <td>86</td>
                  <td>17.41</td>
                  <td>121.44</td>
                  <td>72.40</td>
                  <td>1.83</td>
                </tr>
                <tr>
                  <td>185</td>
                  <td>palauig</td>
                  <td>92</td>
                  <td>PH</td>
                  <td>1528905413</td>
                  <td>100</td>
                  <td>15.44</td>
                  <td>119.90</td>
                  <td>74.11</td>
                  <td>10.67</td>
                </tr>
                <tr>
                  <td>186</td>
                  <td>komsomolskiy</td>
                  <td>0</td>
                  <td>RU</td>
                  <td>1528905413</td>
                  <td>84</td>
                  <td>67.55</td>
                  <td>63.78</td>
                  <td>37.39</td>
                  <td>9.22</td>
                </tr>
                <tr>
                  <td>187</td>
                  <td>atuona</td>
                  <td>44</td>
                  <td>PF</td>
                  <td>1528905298</td>
                  <td>100</td>
                  <td>-9.80</td>
                  <td>-139.03</td>
                  <td>79.60</td>
                  <td>12.91</td>
                </tr>
                <tr>
                  <td>188</td>
                  <td>sinnamary</td>
                  <td>92</td>
                  <td>GF</td>
                  <td>1528905414</td>
                  <td>100</td>
                  <td>5.38</td>
                  <td>-52.96</td>
                  <td>75.19</td>
                  <td>3.40</td>
                </tr>
                <tr>
                  <td>189</td>
                  <td>kavieng</td>
                  <td>92</td>
                  <td>PG</td>
                  <td>1528905414</td>
                  <td>100</td>
                  <td>-2.57</td>
                  <td>150.80</td>
                  <td>78.97</td>
                  <td>5.41</td>
                </tr>
                <tr>
                  <td>190</td>
                  <td>moron</td>
                  <td>0</td>
                  <td>VE</td>
                  <td>1528905415</td>
                  <td>70</td>
                  <td>10.49</td>
                  <td>-68.20</td>
                  <td>81.67</td>
                  <td>3.06</td>
                </tr>
                <tr>
                  <td>191</td>
                  <td>fortuna</td>
                  <td>20</td>
                  <td>ES</td>
                  <td>1528903800</td>
                  <td>64</td>
                  <td>38.18</td>
                  <td>-1.13</td>
                  <td>86.00</td>
                  <td>12.75</td>
                </tr>
                <tr>
                  <td>192</td>
                  <td>pangnirtung</td>
                  <td>90</td>
                  <td>CA</td>
                  <td>1528902000</td>
                  <td>93</td>
                  <td>66.15</td>
                  <td>-65.72</td>
                  <td>35.60</td>
                  <td>4.70</td>
                </tr>
                <tr>
                  <td>193</td>
                  <td>paamiut</td>
                  <td>68</td>
                  <td>GL</td>
                  <td>1528905416</td>
                  <td>100</td>
                  <td>61.99</td>
                  <td>-49.67</td>
                  <td>35.32</td>
                  <td>12.46</td>
                </tr>
                <tr>
                  <td>194</td>
                  <td>juegang</td>
                  <td>36</td>
                  <td>CN</td>
                  <td>1528905417</td>
                  <td>76</td>
                  <td>32.31</td>
                  <td>121.18</td>
                  <td>75.28</td>
                  <td>16.60</td>
                </tr>
                <tr>
                  <td>195</td>
                  <td>kiama</td>
                  <td>0</td>
                  <td>AU</td>
                  <td>1528905418</td>
                  <td>86</td>
                  <td>-34.67</td>
                  <td>150.86</td>
                  <td>50.44</td>
                  <td>6.87</td>
                </tr>
                <tr>
                  <td>196</td>
                  <td>yamada</td>
                  <td>20</td>
                  <td>JP</td>
                  <td>1528902000</td>
                  <td>72</td>
                  <td>36.58</td>
                  <td>137.08</td>
                  <td>60.80</td>
                  <td>14.99</td>
                </tr>
                <tr>
                  <td>197</td>
                  <td>russell</td>
                  <td>0</td>
                  <td>AR</td>
                  <td>1528902000</td>
                  <td>48</td>
                  <td>-33.01</td>
                  <td>-68.80</td>
                  <td>42.80</td>
                  <td>3.36</td>
                </tr>
                <tr>
                  <td>198</td>
                  <td>port hawkesbury</td>
                  <td>1</td>
                  <td>CA</td>
                  <td>1528902000</td>
                  <td>63</td>
                  <td>45.62</td>
                  <td>-61.36</td>
                  <td>64.40</td>
                  <td>16.11</td>
                </tr>
                <tr>
                  <td>199</td>
                  <td>naze</td>
                  <td>75</td>
                  <td>NG</td>
                  <td>1528902000</td>
                  <td>62</td>
                  <td>5.43</td>
                  <td>7.07</td>
                  <td>89.60</td>
                  <td>9.17</td>
                </tr>
                <tr>
                  <td>200</td>
                  <td>namibe</td>
                  <td>0</td>
                  <td>AO</td>
                  <td>1528905419</td>
                  <td>89</td>
                  <td>-15.19</td>
                  <td>12.15</td>
                  <td>74.02</td>
                  <td>17.49</td>
                </tr>
                <tr>
                  <td>201</td>
                  <td>lodja</td>
                  <td>0</td>
                  <td>CD</td>
                  <td>1528905419</td>
                  <td>20</td>
                  <td>-3.52</td>
                  <td>23.60</td>
                  <td>94.36</td>
                  <td>4.97</td>
                </tr>
                <tr>
                  <td>202</td>
                  <td>basco</td>
                  <td>1</td>
                  <td>US</td>
                  <td>1528904100</td>
                  <td>44</td>
                  <td>40.33</td>
                  <td>-91.20</td>
                  <td>77.00</td>
                  <td>13.87</td>
                </tr>
                <tr>
                  <td>203</td>
                  <td>suleja</td>
                  <td>20</td>
                  <td>NG</td>
                  <td>1528905420</td>
                  <td>74</td>
                  <td>9.18</td>
                  <td>7.18</td>
                  <td>87.34</td>
                  <td>2.95</td>
                </tr>
                <tr>
                  <td>204</td>
                  <td>tazovskiy</td>
                  <td>12</td>
                  <td>RU</td>
                  <td>1528905420</td>
                  <td>60</td>
                  <td>67.47</td>
                  <td>78.70</td>
                  <td>67.72</td>
                  <td>14.81</td>
                </tr>
                <tr>
                  <td>205</td>
                  <td>waterloo</td>
                  <td>75</td>
                  <td>CA</td>
                  <td>1528902000</td>
                  <td>78</td>
                  <td>43.47</td>
                  <td>-80.52</td>
                  <td>75.20</td>
                  <td>12.75</td>
                </tr>
                <tr>
                  <td>206</td>
                  <td>kruisfontein</td>
                  <td>0</td>
                  <td>ZA</td>
                  <td>1528905421</td>
                  <td>47</td>
                  <td>-34.00</td>
                  <td>24.73</td>
                  <td>75.82</td>
                  <td>8.43</td>
                </tr>
                <tr>
                  <td>207</td>
                  <td>hithadhoo</td>
                  <td>12</td>
                  <td>MV</td>
                  <td>1528905421</td>
                  <td>100</td>
                  <td>-0.60</td>
                  <td>73.08</td>
                  <td>83.65</td>
                  <td>6.42</td>
                </tr>
                <tr>
                  <td>208</td>
                  <td>aqtobe</td>
                  <td>0</td>
                  <td>KZ</td>
                  <td>1528902000</td>
                  <td>24</td>
                  <td>50.28</td>
                  <td>57.21</td>
                  <td>71.60</td>
                  <td>6.71</td>
                </tr>
                <tr>
                  <td>209</td>
                  <td>trinidad</td>
                  <td>75</td>
                  <td>UY</td>
                  <td>1528902000</td>
                  <td>76</td>
                  <td>-33.52</td>
                  <td>-56.90</td>
                  <td>50.00</td>
                  <td>17.22</td>
                </tr>
                <tr>
                  <td>210</td>
                  <td>jasper</td>
                  <td>12</td>
                  <td>US</td>
                  <td>1528904100</td>
                  <td>83</td>
                  <td>33.83</td>
                  <td>-87.28</td>
                  <td>78.80</td>
                  <td>5.19</td>
                </tr>
                <tr>
                  <td>211</td>
                  <td>tempio pausania</td>
                  <td>40</td>
                  <td>IT</td>
                  <td>1528903800</td>
                  <td>77</td>
                  <td>40.90</td>
                  <td>9.10</td>
                  <td>69.80</td>
                  <td>11.41</td>
                </tr>
                <tr>
                  <td>212</td>
                  <td>kununurra</td>
                  <td>75</td>
                  <td>AU</td>
                  <td>1528902000</td>
                  <td>73</td>
                  <td>-15.77</td>
                  <td>128.74</td>
                  <td>73.40</td>
                  <td>5.82</td>
                </tr>
                <tr>
                  <td>213</td>
                  <td>zhob</td>
                  <td>0</td>
                  <td>PK</td>
                  <td>1528905423</td>
                  <td>10</td>
                  <td>31.34</td>
                  <td>69.45</td>
                  <td>80.95</td>
                  <td>5.64</td>
                </tr>
                <tr>
                  <td>214</td>
                  <td>los llanos de aridane</td>
                  <td>20</td>
                  <td>ES</td>
                  <td>1528903800</td>
                  <td>60</td>
                  <td>28.66</td>
                  <td>-17.92</td>
                  <td>73.40</td>
                  <td>12.75</td>
                </tr>
                <tr>
                  <td>215</td>
                  <td>nohar</td>
                  <td>0</td>
                  <td>IN</td>
                  <td>1528905423</td>
                  <td>22</td>
                  <td>29.18</td>
                  <td>74.77</td>
                  <td>98.50</td>
                  <td>9.55</td>
                </tr>
                <tr>
                  <td>216</td>
                  <td>sainte-suzanne</td>
                  <td>76</td>
                  <td>CH</td>
                  <td>1528903800</td>
                  <td>48</td>
                  <td>47.51</td>
                  <td>6.77</td>
                  <td>66.20</td>
                  <td>10.29</td>
                </tr>
                <tr>
                  <td>217</td>
                  <td>crotone</td>
                  <td>0</td>
                  <td>IT</td>
                  <td>1528901400</td>
                  <td>42</td>
                  <td>39.09</td>
                  <td>17.12</td>
                  <td>82.40</td>
                  <td>23.04</td>
                </tr>
                <tr>
                  <td>218</td>
                  <td>gambela</td>
                  <td>92</td>
                  <td>ET</td>
                  <td>1528905424</td>
                  <td>94</td>
                  <td>8.25</td>
                  <td>34.59</td>
                  <td>68.62</td>
                  <td>2.95</td>
                </tr>
                <tr>
                  <td>219</td>
                  <td>kavaratti</td>
                  <td>80</td>
                  <td>IN</td>
                  <td>1528905424</td>
                  <td>100</td>
                  <td>10.57</td>
                  <td>72.64</td>
                  <td>81.67</td>
                  <td>22.64</td>
                </tr>
                <tr>
                  <td>220</td>
                  <td>ust-ilimsk</td>
                  <td>12</td>
                  <td>RU</td>
                  <td>1528905425</td>
                  <td>87</td>
                  <td>57.96</td>
                  <td>102.73</td>
                  <td>60.61</td>
                  <td>1.95</td>
                </tr>
                <tr>
                  <td>221</td>
                  <td>leo</td>
                  <td>0</td>
                  <td>BF</td>
                  <td>1528905429</td>
                  <td>66</td>
                  <td>11.10</td>
                  <td>-2.10</td>
                  <td>94.72</td>
                  <td>4.63</td>
                </tr>
                <tr>
                  <td>222</td>
                  <td>totolapan</td>
                  <td>75</td>
                  <td>MX</td>
                  <td>1528902840</td>
                  <td>77</td>
                  <td>18.99</td>
                  <td>-98.92</td>
                  <td>59.00</td>
                  <td>5.82</td>
                </tr>
                <tr>
                  <td>223</td>
                  <td>funtua</td>
                  <td>44</td>
                  <td>NG</td>
                  <td>1528905429</td>
                  <td>50</td>
                  <td>11.52</td>
                  <td>7.31</td>
                  <td>90.67</td>
                  <td>2.17</td>
                </tr>
                <tr>
                  <td>224</td>
                  <td>salalah</td>
                  <td>75</td>
                  <td>OM</td>
                  <td>1528901400</td>
                  <td>89</td>
                  <td>17.01</td>
                  <td>54.10</td>
                  <td>84.20</td>
                  <td>10.29</td>
                </tr>
                <tr>
                  <td>225</td>
                  <td>burnie</td>
                  <td>92</td>
                  <td>AU</td>
                  <td>1528905430</td>
                  <td>100</td>
                  <td>-41.05</td>
                  <td>145.91</td>
                  <td>51.88</td>
                  <td>21.07</td>
                </tr>
                <tr>
                  <td>226</td>
                  <td>boulder city</td>
                  <td>1</td>
                  <td>US</td>
                  <td>1528902900</td>
                  <td>11</td>
                  <td>35.98</td>
                  <td>-114.83</td>
                  <td>89.60</td>
                  <td>3.51</td>
                </tr>
                <tr>
                  <td>227</td>
                  <td>massakory</td>
                  <td>0</td>
                  <td>TD</td>
                  <td>1528905431</td>
                  <td>46</td>
                  <td>13.00</td>
                  <td>15.73</td>
                  <td>100.21</td>
                  <td>6.98</td>
                </tr>
                <tr>
                  <td>228</td>
                  <td>arlit</td>
                  <td>0</td>
                  <td>NE</td>
                  <td>1528905432</td>
                  <td>14</td>
                  <td>18.74</td>
                  <td>7.39</td>
                  <td>110.92</td>
                  <td>4.74</td>
                </tr>
                <tr>
                  <td>229</td>
                  <td>zhigansk</td>
                  <td>0</td>
                  <td>RU</td>
                  <td>1528905432</td>
                  <td>56</td>
                  <td>66.77</td>
                  <td>123.37</td>
                  <td>56.83</td>
                  <td>4.97</td>
                </tr>
                <tr>
                  <td>230</td>
                  <td>florianopolis</td>
                  <td>40</td>
                  <td>BR</td>
                  <td>1528902000</td>
                  <td>64</td>
                  <td>-27.60</td>
                  <td>-48.55</td>
                  <td>69.80</td>
                  <td>3.36</td>
                </tr>
                <tr>
                  <td>231</td>
                  <td>lavrentiya</td>
                  <td>0</td>
                  <td>RU</td>
                  <td>1528905432</td>
                  <td>76</td>
                  <td>65.58</td>
                  <td>-170.99</td>
                  <td>35.95</td>
                  <td>8.43</td>
                </tr>
                <tr>
                  <td>232</td>
                  <td>bluefield</td>
                  <td>90</td>
                  <td>US</td>
                  <td>1528902900</td>
                  <td>78</td>
                  <td>37.27</td>
                  <td>-81.22</td>
                  <td>78.80</td>
                  <td>11.41</td>
                </tr>
                <tr>
                  <td>233</td>
                  <td>te anau</td>
                  <td>8</td>
                  <td>NZ</td>
                  <td>1528905433</td>
                  <td>80</td>
                  <td>-45.41</td>
                  <td>167.72</td>
                  <td>27.22</td>
                  <td>2.84</td>
                </tr>
                <tr>
                  <td>234</td>
                  <td>marawi</td>
                  <td>44</td>
                  <td>PH</td>
                  <td>1528905433</td>
                  <td>99</td>
                  <td>8.00</td>
                  <td>124.29</td>
                  <td>66.73</td>
                  <td>2.28</td>
                </tr>
                <tr>
                  <td>235</td>
                  <td>amapa</td>
                  <td>75</td>
                  <td>HN</td>
                  <td>1528905600</td>
                  <td>83</td>
                  <td>15.09</td>
                  <td>-87.97</td>
                  <td>84.20</td>
                  <td>4.70</td>
                </tr>
                <tr>
                  <td>236</td>
                  <td>palmer</td>
                  <td>75</td>
                  <td>AU</td>
                  <td>1528902000</td>
                  <td>82</td>
                  <td>-34.85</td>
                  <td>139.16</td>
                  <td>55.40</td>
                  <td>17.22</td>
                </tr>
                <tr>
                  <td>237</td>
                  <td>cidreira</td>
                  <td>0</td>
                  <td>BR</td>
                  <td>1528905434</td>
                  <td>81</td>
                  <td>-30.17</td>
                  <td>-50.22</td>
                  <td>51.97</td>
                  <td>26.33</td>
                </tr>
                <tr>
                  <td>238</td>
                  <td>saint-pierre</td>
                  <td>90</td>
                  <td>FR</td>
                  <td>1528903800</td>
                  <td>67</td>
                  <td>48.95</td>
                  <td>4.24</td>
                  <td>66.20</td>
                  <td>12.75</td>
                </tr>
                <tr>
                  <td>239</td>
                  <td>aykhal</td>
                  <td>32</td>
                  <td>RU</td>
                  <td>1528905439</td>
                  <td>57</td>
                  <td>65.95</td>
                  <td>111.51</td>
                  <td>62.23</td>
                  <td>4.74</td>
                </tr>
                <tr>
                  <td>240</td>
                  <td>ondangwa</td>
                  <td>0</td>
                  <td>NaN</td>
                  <td>1528902000</td>
                  <td>13</td>
                  <td>-17.91</td>
                  <td>15.98</td>
                  <td>84.20</td>
                  <td>2.24</td>
                </tr>
                <tr>
                  <td>241</td>
                  <td>pitimbu</td>
                  <td>40</td>
                  <td>BR</td>
                  <td>1528902000</td>
                  <td>54</td>
                  <td>-7.47</td>
                  <td>-34.81</td>
                  <td>84.20</td>
                  <td>17.22</td>
                </tr>
                <tr>
                  <td>242</td>
                  <td>grandview</td>
                  <td>1</td>
                  <td>US</td>
                  <td>1528905300</td>
                  <td>65</td>
                  <td>38.89</td>
                  <td>-94.53</td>
                  <td>80.60</td>
                  <td>10.29</td>
                </tr>
                <tr>
                  <td>243</td>
                  <td>williston</td>
                  <td>1</td>
                  <td>US</td>
                  <td>1528902900</td>
                  <td>36</td>
                  <td>48.15</td>
                  <td>-103.62</td>
                  <td>71.60</td>
                  <td>8.05</td>
                </tr>
                <tr>
                  <td>244</td>
                  <td>maniitsoq</td>
                  <td>68</td>
                  <td>GL</td>
                  <td>1528905442</td>
                  <td>97</td>
                  <td>65.42</td>
                  <td>-52.90</td>
                  <td>36.31</td>
                  <td>5.53</td>
                </tr>
                <tr>
                  <td>245</td>
                  <td>krasnyy yar</td>
                  <td>92</td>
                  <td>RU</td>
                  <td>1528905443</td>
                  <td>86</td>
                  <td>50.70</td>
                  <td>44.73</td>
                  <td>64.03</td>
                  <td>8.21</td>
                </tr>
                <tr>
                  <td>246</td>
                  <td>nouadhibou</td>
                  <td>20</td>
                  <td>MR</td>
                  <td>1528902000</td>
                  <td>47</td>
                  <td>20.93</td>
                  <td>-17.03</td>
                  <td>80.60</td>
                  <td>14.99</td>
                </tr>
                <tr>
                  <td>247</td>
                  <td>buritama</td>
                  <td>68</td>
                  <td>BR</td>
                  <td>1528905444</td>
                  <td>95</td>
                  <td>-21.07</td>
                  <td>-50.14</td>
                  <td>75.10</td>
                  <td>6.31</td>
                </tr>
                <tr>
                  <td>248</td>
                  <td>longyearbyen</td>
                  <td>90</td>
                  <td>NO</td>
                  <td>1528901400</td>
                  <td>86</td>
                  <td>78.22</td>
                  <td>15.63</td>
                  <td>33.80</td>
                  <td>18.34</td>
                </tr>
                <tr>
                  <td>249</td>
                  <td>lasa</td>
                  <td>20</td>
                  <td>CY</td>
                  <td>1528903800</td>
                  <td>74</td>
                  <td>34.92</td>
                  <td>32.53</td>
                  <td>80.60</td>
                  <td>6.93</td>
                </tr>
                <tr>
                  <td>250</td>
                  <td>college</td>
                  <td>1</td>
                  <td>US</td>
                  <td>1528901880</td>
                  <td>75</td>
                  <td>64.86</td>
                  <td>-147.80</td>
                  <td>42.80</td>
                  <td>3.36</td>
                </tr>
                <tr>
                  <td>251</td>
                  <td>ust-tsilma</td>
                  <td>12</td>
                  <td>RU</td>
                  <td>1528905445</td>
                  <td>84</td>
                  <td>65.44</td>
                  <td>52.15</td>
                  <td>54.40</td>
                  <td>3.62</td>
                </tr>
                <tr>
                  <td>252</td>
                  <td>saint-augustin</td>
                  <td>64</td>
                  <td>FR</td>
                  <td>1528903800</td>
                  <td>82</td>
                  <td>44.83</td>
                  <td>-0.61</td>
                  <td>69.80</td>
                  <td>12.75</td>
                </tr>
                <tr>
                  <td>253</td>
                  <td>berlevag</td>
                  <td>75</td>
                  <td>NO</td>
                  <td>1528901400</td>
                  <td>70</td>
                  <td>70.86</td>
                  <td>29.09</td>
                  <td>42.80</td>
                  <td>13.87</td>
                </tr>
                <tr>
                  <td>254</td>
                  <td>havoysund</td>
                  <td>75</td>
                  <td>NO</td>
                  <td>1528903200</td>
                  <td>87</td>
                  <td>71.00</td>
                  <td>24.66</td>
                  <td>42.80</td>
                  <td>13.87</td>
                </tr>
                <tr>
                  <td>255</td>
                  <td>kamina</td>
                  <td>0</td>
                  <td>CD</td>
                  <td>1528905450</td>
                  <td>23</td>
                  <td>-8.74</td>
                  <td>25.00</td>
                  <td>85.00</td>
                  <td>7.99</td>
                </tr>
                <tr>
                  <td>256</td>
                  <td>yaan</td>
                  <td>48</td>
                  <td>NG</td>
                  <td>1528905450</td>
                  <td>100</td>
                  <td>7.38</td>
                  <td>8.57</td>
                  <td>85.90</td>
                  <td>7.09</td>
                </tr>
                <tr>
                  <td>257</td>
                  <td>makakilo city</td>
                  <td>1</td>
                  <td>US</td>
                  <td>1528901820</td>
                  <td>83</td>
                  <td>21.35</td>
                  <td>-158.09</td>
                  <td>77.00</td>
                  <td>4.70</td>
                </tr>
                <tr>
                  <td>258</td>
                  <td>along</td>
                  <td>100</td>
                  <td>IN</td>
                  <td>1528905450</td>
                  <td>98</td>
                  <td>28.17</td>
                  <td>94.80</td>
                  <td>68.89</td>
                  <td>1.50</td>
                </tr>
                <tr>
                  <td>259</td>
                  <td>vanimo</td>
                  <td>88</td>
                  <td>PG</td>
                  <td>1528905451</td>
                  <td>100</td>
                  <td>-2.67</td>
                  <td>141.30</td>
                  <td>83.65</td>
                  <td>4.29</td>
                </tr>
                <tr>
                  <td>260</td>
                  <td>hovd</td>
                  <td>75</td>
                  <td>NO</td>
                  <td>1528903200</td>
                  <td>48</td>
                  <td>63.83</td>
                  <td>10.70</td>
                  <td>62.60</td>
                  <td>4.70</td>
                </tr>
                <tr>
                  <td>261</td>
                  <td>la maddalena</td>
                  <td>40</td>
                  <td>IT</td>
                  <td>1528903200</td>
                  <td>57</td>
                  <td>39.15</td>
                  <td>9.02</td>
                  <td>75.20</td>
                  <td>17.22</td>
                </tr>
                <tr>
                  <td>262</td>
                  <td>grand gaube</td>
                  <td>75</td>
                  <td>MU</td>
                  <td>1528902000</td>
                  <td>69</td>
                  <td>-20.01</td>
                  <td>57.66</td>
                  <td>75.20</td>
                  <td>14.99</td>
                </tr>
                <tr>
                  <td>263</td>
                  <td>novoagansk</td>
                  <td>20</td>
                  <td>RU</td>
                  <td>1528905453</td>
                  <td>37</td>
                  <td>61.94</td>
                  <td>76.66</td>
                  <td>67.81</td>
                  <td>8.43</td>
                </tr>
                <tr>
                  <td>264</td>
                  <td>kearney</td>
                  <td>90</td>
                  <td>US</td>
                  <td>1528902900</td>
                  <td>64</td>
                  <td>40.70</td>
                  <td>-99.08</td>
                  <td>71.60</td>
                  <td>14.99</td>
                </tr>
                <tr>
                  <td>265</td>
                  <td>geraldton</td>
                  <td>75</td>
                  <td>CA</td>
                  <td>1528902000</td>
                  <td>63</td>
                  <td>49.72</td>
                  <td>-86.95</td>
                  <td>62.60</td>
                  <td>8.05</td>
                </tr>
                <tr>
                  <td>266</td>
                  <td>castro</td>
                  <td>0</td>
                  <td>CL</td>
                  <td>1528905454</td>
                  <td>99</td>
                  <td>-42.48</td>
                  <td>-73.76</td>
                  <td>39.73</td>
                  <td>2.73</td>
                </tr>
                <tr>
                  <td>267</td>
                  <td>luganville</td>
                  <td>92</td>
                  <td>VU</td>
                  <td>1528905455</td>
                  <td>100</td>
                  <td>-15.51</td>
                  <td>167.18</td>
                  <td>75.19</td>
                  <td>4.85</td>
                </tr>
                <tr>
                  <td>268</td>
                  <td>mahebourg</td>
                  <td>75</td>
                  <td>MU</td>
                  <td>1528902000</td>
                  <td>69</td>
                  <td>-20.41</td>
                  <td>57.70</td>
                  <td>75.20</td>
                  <td>14.99</td>
                </tr>
                <tr>
                  <td>269</td>
                  <td>vostok</td>
                  <td>44</td>
                  <td>RU</td>
                  <td>1528905455</td>
                  <td>83</td>
                  <td>46.45</td>
                  <td>135.83</td>
                  <td>45.04</td>
                  <td>1.95</td>
                </tr>
                <tr>
                  <td>270</td>
                  <td>esperance</td>
                  <td>75</td>
                  <td>TT</td>
                  <td>1528902000</td>
                  <td>88</td>
                  <td>10.24</td>
                  <td>-61.45</td>
                  <td>80.60</td>
                  <td>12.75</td>
                </tr>
                <tr>
                  <td>271</td>
                  <td>fare</td>
                  <td>0</td>
                  <td>PF</td>
                  <td>1528905456</td>
                  <td>100</td>
                  <td>-16.70</td>
                  <td>-151.02</td>
                  <td>79.42</td>
                  <td>13.91</td>
                </tr>
                <tr>
                  <td>272</td>
                  <td>toora-khem</td>
                  <td>92</td>
                  <td>RU</td>
                  <td>1528905456</td>
                  <td>83</td>
                  <td>52.47</td>
                  <td>96.11</td>
                  <td>57.82</td>
                  <td>2.84</td>
                </tr>
                <tr>
                  <td>273</td>
                  <td>santa rita</td>
                  <td>36</td>
                  <td>VE</td>
                  <td>1528905458</td>
                  <td>64</td>
                  <td>10.21</td>
                  <td>-67.56</td>
                  <td>83.65</td>
                  <td>2.73</td>
                </tr>
                <tr>
                  <td>274</td>
                  <td>west bay</td>
                  <td>40</td>
                  <td>GB</td>
                  <td>1528903200</td>
                  <td>77</td>
                  <td>50.71</td>
                  <td>-2.76</td>
                  <td>68.00</td>
                  <td>12.75</td>
                </tr>
                <tr>
                  <td>275</td>
                  <td>gamba</td>
                  <td>92</td>
                  <td>CN</td>
                  <td>1528905459</td>
                  <td>91</td>
                  <td>28.28</td>
                  <td>88.52</td>
                  <td>32.35</td>
                  <td>2.28</td>
                </tr>
                <tr>
                  <td>276</td>
                  <td>rudnya</td>
                  <td>92</td>
                  <td>RU</td>
                  <td>1528905459</td>
                  <td>88</td>
                  <td>50.80</td>
                  <td>44.56</td>
                  <td>63.31</td>
                  <td>7.65</td>
                </tr>
                <tr>
                  <td>277</td>
                  <td>norman wells</td>
                  <td>90</td>
                  <td>CA</td>
                  <td>1528902000</td>
                  <td>65</td>
                  <td>65.28</td>
                  <td>-126.83</td>
                  <td>44.60</td>
                  <td>5.82</td>
                </tr>
                <tr>
                  <td>278</td>
                  <td>salinas</td>
                  <td>1</td>
                  <td>US</td>
                  <td>1528904100</td>
                  <td>67</td>
                  <td>36.67</td>
                  <td>-121.66</td>
                  <td>60.80</td>
                  <td>3.62</td>
                </tr>
                <tr>
                  <td>279</td>
                  <td>ugoofaaru</td>
                  <td>80</td>
                  <td>MV</td>
                  <td>1528905461</td>
                  <td>100</td>
                  <td>5.67</td>
                  <td>73.00</td>
                  <td>82.93</td>
                  <td>8.77</td>
                </tr>
                <tr>
                  <td>280</td>
                  <td>kiunga</td>
                  <td>88</td>
                  <td>PG</td>
                  <td>1528905464</td>
                  <td>94</td>
                  <td>-6.12</td>
                  <td>141.30</td>
                  <td>74.29</td>
                  <td>2.06</td>
                </tr>
                <tr>
                  <td>281</td>
                  <td>koumac</td>
                  <td>76</td>
                  <td>NC</td>
                  <td>1528905465</td>
                  <td>96</td>
                  <td>-20.56</td>
                  <td>164.28</td>
                  <td>67.90</td>
                  <td>4.07</td>
                </tr>
                <tr>
                  <td>282</td>
                  <td>adre</td>
                  <td>20</td>
                  <td>TD</td>
                  <td>1528905465</td>
                  <td>16</td>
                  <td>13.47</td>
                  <td>22.20</td>
                  <td>103.27</td>
                  <td>8.66</td>
                </tr>
                <tr>
                  <td>283</td>
                  <td>ahtopol</td>
                  <td>0</td>
                  <td>BG</td>
                  <td>1528903800</td>
                  <td>57</td>
                  <td>42.10</td>
                  <td>27.94</td>
                  <td>77.00</td>
                  <td>13.87</td>
                </tr>
                <tr>
                  <td>284</td>
                  <td>slantsy</td>
                  <td>0</td>
                  <td>RU</td>
                  <td>1528905466</td>
                  <td>55</td>
                  <td>59.12</td>
                  <td>28.09</td>
                  <td>62.50</td>
                  <td>4.18</td>
                </tr>
                <tr>
                  <td>285</td>
                  <td>mallaig</td>
                  <td>92</td>
                  <td>GB</td>
                  <td>1528905466</td>
                  <td>99</td>
                  <td>57.01</td>
                  <td>-5.83</td>
                  <td>53.95</td>
                  <td>24.09</td>
                </tr>
                <tr>
                  <td>286</td>
                  <td>auch</td>
                  <td>40</td>
                  <td>FR</td>
                  <td>1528903800</td>
                  <td>56</td>
                  <td>43.65</td>
                  <td>0.59</td>
                  <td>73.40</td>
                  <td>10.29</td>
                </tr>
                <tr>
                  <td>287</td>
                  <td>pathein</td>
                  <td>92</td>
                  <td>MM</td>
                  <td>1528905467</td>
                  <td>96</td>
                  <td>16.78</td>
                  <td>94.73</td>
                  <td>76.90</td>
                  <td>14.81</td>
                </tr>
                <tr>
                  <td>288</td>
                  <td>maceio</td>
                  <td>75</td>
                  <td>BR</td>
                  <td>1528905600</td>
                  <td>88</td>
                  <td>-9.67</td>
                  <td>-35.74</td>
                  <td>75.20</td>
                  <td>6.93</td>
                </tr>
                <tr>
                  <td>289</td>
                  <td>oloron-sainte-marie</td>
                  <td>88</td>
                  <td>FR</td>
                  <td>1528903800</td>
                  <td>93</td>
                  <td>43.19</td>
                  <td>-0.61</td>
                  <td>68.00</td>
                  <td>11.41</td>
                </tr>
                <tr>
                  <td>290</td>
                  <td>isangel</td>
                  <td>68</td>
                  <td>VU</td>
                  <td>1528905468</td>
                  <td>100</td>
                  <td>-19.55</td>
                  <td>169.27</td>
                  <td>74.20</td>
                  <td>14.36</td>
                </tr>
                <tr>
                  <td>291</td>
                  <td>manglaur</td>
                  <td>0</td>
                  <td>IN</td>
                  <td>1528905468</td>
                  <td>64</td>
                  <td>29.79</td>
                  <td>77.88</td>
                  <td>82.57</td>
                  <td>2.39</td>
                </tr>
                <tr>
                  <td>292</td>
                  <td>wenling</td>
                  <td>92</td>
                  <td>CN</td>
                  <td>1528905468</td>
                  <td>95</td>
                  <td>28.38</td>
                  <td>121.38</td>
                  <td>74.56</td>
                  <td>3.96</td>
                </tr>
                <tr>
                  <td>293</td>
                  <td>pak phanang</td>
                  <td>48</td>
                  <td>TH</td>
                  <td>1528905469</td>
                  <td>93</td>
                  <td>8.35</td>
                  <td>100.20</td>
                  <td>85.99</td>
                  <td>10.22</td>
                </tr>
                <tr>
                  <td>294</td>
                  <td>aksay</td>
                  <td>0</td>
                  <td>RU</td>
                  <td>1528905469</td>
                  <td>21</td>
                  <td>47.27</td>
                  <td>39.86</td>
                  <td>87.43</td>
                  <td>3.74</td>
                </tr>
                <tr>
                  <td>295</td>
                  <td>baghdad</td>
                  <td>0</td>
                  <td>IQ</td>
                  <td>1528902000</td>
                  <td>14</td>
                  <td>33.30</td>
                  <td>44.38</td>
                  <td>104.00</td>
                  <td>4.70</td>
                </tr>
                <tr>
                  <td>296</td>
                  <td>fort nelson</td>
                  <td>90</td>
                  <td>CA</td>
                  <td>1528902000</td>
                  <td>86</td>
                  <td>58.81</td>
                  <td>-122.69</td>
                  <td>41.00</td>
                  <td>9.17</td>
                </tr>
                <tr>
                  <td>297</td>
                  <td>fuerte olimpo</td>
                  <td>92</td>
                  <td>BR</td>
                  <td>1528905470</td>
                  <td>75</td>
                  <td>-21.04</td>
                  <td>-57.87</td>
                  <td>60.97</td>
                  <td>12.80</td>
                </tr>
                <tr>
                  <td>298</td>
                  <td>bandarban</td>
                  <td>90</td>
                  <td>BD</td>
                  <td>1528902000</td>
                  <td>94</td>
                  <td>22.20</td>
                  <td>92.22</td>
                  <td>80.60</td>
                  <td>13.87</td>
                </tr>
                <tr>
                  <td>299</td>
                  <td>mao</td>
                  <td>40</td>
                  <td>DO</td>
                  <td>1528902000</td>
                  <td>62</td>
                  <td>19.55</td>
                  <td>-71.08</td>
                  <td>89.60</td>
                  <td>12.75</td>
                </tr>
                <tr>
                  <td>300</td>
                  <td>christchurch</td>
                  <td>100</td>
                  <td>NZ</td>
                  <td>1528903800</td>
                  <td>93</td>
                  <td>-43.53</td>
                  <td>172.64</td>
                  <td>48.20</td>
                  <td>8.05</td>
                </tr>
                <tr>
                  <td>301</td>
                  <td>goderich</td>
                  <td>32</td>
                  <td>CA</td>
                  <td>1528905435</td>
                  <td>88</td>
                  <td>43.74</td>
                  <td>-81.71</td>
                  <td>68.17</td>
                  <td>11.45</td>
                </tr>
                <tr>
                  <td>302</td>
                  <td>kizema</td>
                  <td>56</td>
                  <td>RU</td>
                  <td>1528905476</td>
                  <td>66</td>
                  <td>61.11</td>
                  <td>44.83</td>
                  <td>53.86</td>
                  <td>18.39</td>
                </tr>
                <tr>
                  <td>303</td>
                  <td>quatre cocos</td>
                  <td>75</td>
                  <td>MU</td>
                  <td>1528902000</td>
                  <td>69</td>
                  <td>-20.21</td>
                  <td>57.76</td>
                  <td>75.20</td>
                  <td>14.99</td>
                </tr>
                <tr>
                  <td>304</td>
                  <td>kalur kot</td>
                  <td>44</td>
                  <td>PK</td>
                  <td>1528905476</td>
                  <td>41</td>
                  <td>32.16</td>
                  <td>71.27</td>
                  <td>91.03</td>
                  <td>1.95</td>
                </tr>
                <tr>
                  <td>305</td>
                  <td>singaraja</td>
                  <td>64</td>
                  <td>ID</td>
                  <td>1528905476</td>
                  <td>100</td>
                  <td>-8.11</td>
                  <td>115.08</td>
                  <td>66.73</td>
                  <td>1.95</td>
                </tr>
                <tr>
                  <td>306</td>
                  <td>coquimbo</td>
                  <td>0</td>
                  <td>CL</td>
                  <td>1528902000</td>
                  <td>62</td>
                  <td>-29.95</td>
                  <td>-71.34</td>
                  <td>53.60</td>
                  <td>8.05</td>
                </tr>
                <tr>
                  <td>307</td>
                  <td>urengoy</td>
                  <td>12</td>
                  <td>RU</td>
                  <td>1528905477</td>
                  <td>59</td>
                  <td>65.96</td>
                  <td>78.37</td>
                  <td>69.25</td>
                  <td>12.24</td>
                </tr>
                <tr>
                  <td>308</td>
                  <td>yaypan</td>
                  <td>24</td>
                  <td>UZ</td>
                  <td>1528905477</td>
                  <td>43</td>
                  <td>40.38</td>
                  <td>70.82</td>
                  <td>76.54</td>
                  <td>3.62</td>
                </tr>
                <tr>
                  <td>309</td>
                  <td>seoul</td>
                  <td>75</td>
                  <td>KR</td>
                  <td>1528902000</td>
                  <td>68</td>
                  <td>37.57</td>
                  <td>126.98</td>
                  <td>71.60</td>
                  <td>3.36</td>
                </tr>
                <tr>
                  <td>310</td>
                  <td>acopiara</td>
                  <td>0</td>
                  <td>BR</td>
                  <td>1528905477</td>
                  <td>51</td>
                  <td>-6.09</td>
                  <td>-39.45</td>
                  <td>83.20</td>
                  <td>11.23</td>
                </tr>
                <tr>
                  <td>311</td>
                  <td>warrnambool</td>
                  <td>76</td>
                  <td>AU</td>
                  <td>1528905363</td>
                  <td>100</td>
                  <td>-38.38</td>
                  <td>142.48</td>
                  <td>51.43</td>
                  <td>17.72</td>
                </tr>
                <tr>
                  <td>312</td>
                  <td>phan thiet</td>
                  <td>36</td>
                  <td>VN</td>
                  <td>1528905478</td>
                  <td>100</td>
                  <td>10.93</td>
                  <td>108.10</td>
                  <td>78.61</td>
                  <td>10.00</td>
                </tr>
                <tr>
                  <td>313</td>
                  <td>ilebo</td>
                  <td>12</td>
                  <td>CD</td>
                  <td>1528905478</td>
                  <td>22</td>
                  <td>-4.33</td>
                  <td>20.59</td>
                  <td>94.72</td>
                  <td>5.19</td>
                </tr>
                <tr>
                  <td>314</td>
                  <td>kijang</td>
                  <td>40</td>
                  <td>KR</td>
                  <td>1528902000</td>
                  <td>72</td>
                  <td>35.24</td>
                  <td>129.21</td>
                  <td>68.00</td>
                  <td>13.87</td>
                </tr>
                <tr>
                  <td>315</td>
                  <td>krasnogorsk</td>
                  <td>75</td>
                  <td>RU</td>
                  <td>1528902000</td>
                  <td>59</td>
                  <td>55.82</td>
                  <td>37.34</td>
                  <td>69.80</td>
                  <td>13.42</td>
                </tr>
                <tr>
                  <td>316</td>
                  <td>husavik</td>
                  <td>44</td>
                  <td>CA</td>
                  <td>1528905479</td>
                  <td>72</td>
                  <td>50.56</td>
                  <td>-96.99</td>
                  <td>67.27</td>
                  <td>7.31</td>
                </tr>
                <tr>
                  <td>317</td>
                  <td>araouane</td>
                  <td>0</td>
                  <td>ML</td>
                  <td>1528905479</td>
                  <td>15</td>
                  <td>18.90</td>
                  <td>-3.53</td>
                  <td>111.46</td>
                  <td>5.75</td>
                </tr>
                <tr>
                  <td>318</td>
                  <td>tilichiki</td>
                  <td>0</td>
                  <td>RU</td>
                  <td>1528905480</td>
                  <td>88</td>
                  <td>60.47</td>
                  <td>166.10</td>
                  <td>37.93</td>
                  <td>2.62</td>
                </tr>
                <tr>
                  <td>319</td>
                  <td>bosobolo</td>
                  <td>20</td>
                  <td>CD</td>
                  <td>1528905481</td>
                  <td>70</td>
                  <td>4.19</td>
                  <td>19.88</td>
                  <td>84.19</td>
                  <td>6.42</td>
                </tr>
                <tr>
                  <td>320</td>
                  <td>villarrobledo</td>
                  <td>0</td>
                  <td>ES</td>
                  <td>1528905482</td>
                  <td>28</td>
                  <td>39.27</td>
                  <td>-2.60</td>
                  <td>76.99</td>
                  <td>12.01</td>
                </tr>
                <tr>
                  <td>321</td>
                  <td>ribeira grande</td>
                  <td>40</td>
                  <td>PT</td>
                  <td>1528903800</td>
                  <td>83</td>
                  <td>38.52</td>
                  <td>-28.70</td>
                  <td>75.20</td>
                  <td>11.41</td>
                </tr>
                <tr>
                  <td>322</td>
                  <td>shakawe</td>
                  <td>0</td>
                  <td>BW</td>
                  <td>1528905485</td>
                  <td>23</td>
                  <td>-18.36</td>
                  <td>21.84</td>
                  <td>73.93</td>
                  <td>5.19</td>
                </tr>
                <tr>
                  <td>323</td>
                  <td>nemuro</td>
                  <td>80</td>
                  <td>JP</td>
                  <td>1528905486</td>
                  <td>100</td>
                  <td>43.32</td>
                  <td>145.57</td>
                  <td>48.64</td>
                  <td>17.83</td>
                </tr>
                <tr>
                  <td>324</td>
                  <td>miramar</td>
                  <td>0</td>
                  <td>CR</td>
                  <td>1528902000</td>
                  <td>61</td>
                  <td>10.09</td>
                  <td>-84.73</td>
                  <td>80.60</td>
                  <td>3.36</td>
                </tr>
                <tr>
                  <td>325</td>
                  <td>kerman</td>
                  <td>20</td>
                  <td>IR</td>
                  <td>1528902000</td>
                  <td>5</td>
                  <td>30.29</td>
                  <td>57.06</td>
                  <td>91.40</td>
                  <td>13.87</td>
                </tr>
                <tr>
                  <td>326</td>
                  <td>davidson</td>
                  <td>40</td>
                  <td>US</td>
                  <td>1528905600</td>
                  <td>65</td>
                  <td>35.50</td>
                  <td>-80.85</td>
                  <td>78.80</td>
                  <td>4.70</td>
                </tr>
                <tr>
                  <td>327</td>
                  <td>oksfjord</td>
                  <td>40</td>
                  <td>NO</td>
                  <td>1528903200</td>
                  <td>65</td>
                  <td>70.24</td>
                  <td>22.35</td>
                  <td>46.40</td>
                  <td>10.29</td>
                </tr>
                <tr>
                  <td>328</td>
                  <td>wattegama</td>
                  <td>92</td>
                  <td>LK</td>
                  <td>1528905487</td>
                  <td>97</td>
                  <td>7.35</td>
                  <td>80.68</td>
                  <td>71.41</td>
                  <td>5.75</td>
                </tr>
                <tr>
                  <td>329</td>
                  <td>inyonga</td>
                  <td>0</td>
                  <td>TZ</td>
                  <td>1528905487</td>
                  <td>32</td>
                  <td>-6.72</td>
                  <td>32.06</td>
                  <td>79.42</td>
                  <td>3.18</td>
                </tr>
                <tr>
                  <td>330</td>
                  <td>saint george</td>
                  <td>40</td>
                  <td>GR</td>
                  <td>1528903200</td>
                  <td>54</td>
                  <td>39.45</td>
                  <td>22.34</td>
                  <td>80.60</td>
                  <td>8.05</td>
                </tr>
                <tr>
                  <td>331</td>
                  <td>jabinyanah</td>
                  <td>0</td>
                  <td>TN</td>
                  <td>1528902000</td>
                  <td>47</td>
                  <td>35.03</td>
                  <td>10.91</td>
                  <td>80.60</td>
                  <td>13.87</td>
                </tr>
                <tr>
                  <td>332</td>
                  <td>siddipet</td>
                  <td>56</td>
                  <td>IN</td>
                  <td>1528905488</td>
                  <td>58</td>
                  <td>18.10</td>
                  <td>78.85</td>
                  <td>84.10</td>
                  <td>11.68</td>
                </tr>
                <tr>
                  <td>333</td>
                  <td>praia da vitoria</td>
                  <td>40</td>
                  <td>PT</td>
                  <td>1528902000</td>
                  <td>78</td>
                  <td>38.73</td>
                  <td>-27.07</td>
                  <td>75.20</td>
                  <td>10.22</td>
                </tr>
                <tr>
                  <td>334</td>
                  <td>duluth</td>
                  <td>1</td>
                  <td>US</td>
                  <td>1528904100</td>
                  <td>46</td>
                  <td>46.77</td>
                  <td>-92.13</td>
                  <td>73.40</td>
                  <td>8.05</td>
                </tr>
                <tr>
                  <td>335</td>
                  <td>oistins</td>
                  <td>20</td>
                  <td>BB</td>
                  <td>1528902000</td>
                  <td>66</td>
                  <td>13.07</td>
                  <td>-59.53</td>
                  <td>86.00</td>
                  <td>25.28</td>
                </tr>
                <tr>
                  <td>336</td>
                  <td>san onofre</td>
                  <td>0</td>
                  <td>CO</td>
                  <td>1528905495</td>
                  <td>93</td>
                  <td>9.74</td>
                  <td>-75.52</td>
                  <td>86.44</td>
                  <td>5.30</td>
                </tr>
                <tr>
                  <td>337</td>
                  <td>avera</td>
                  <td>90</td>
                  <td>US</td>
                  <td>1528904100</td>
                  <td>83</td>
                  <td>33.19</td>
                  <td>-82.53</td>
                  <td>78.80</td>
                  <td>3.74</td>
                </tr>
                <tr>
                  <td>338</td>
                  <td>alizai</td>
                  <td>0</td>
                  <td>PK</td>
                  <td>1528905496</td>
                  <td>30</td>
                  <td>33.94</td>
                  <td>71.55</td>
                  <td>89.77</td>
                  <td>3.29</td>
                </tr>
                <tr>
                  <td>339</td>
                  <td>bela</td>
                  <td>36</td>
                  <td>PK</td>
                  <td>1528905496</td>
                  <td>29</td>
                  <td>26.23</td>
                  <td>66.31</td>
                  <td>93.37</td>
                  <td>10.33</td>
                </tr>
                <tr>
                  <td>340</td>
                  <td>kalas</td>
                  <td>0</td>
                  <td>PK</td>
                  <td>1528903800</td>
                  <td>25</td>
                  <td>33.49</td>
                  <td>72.96</td>
                  <td>98.60</td>
                  <td>4.97</td>
                </tr>
                <tr>
                  <td>341</td>
                  <td>gisborne</td>
                  <td>12</td>
                  <td>NZ</td>
                  <td>1528905498</td>
                  <td>86</td>
                  <td>-38.66</td>
                  <td>178.02</td>
                  <td>52.60</td>
                  <td>10.67</td>
                </tr>
                <tr>
                  <td>342</td>
                  <td>yuryevets</td>
                  <td>24</td>
                  <td>RU</td>
                  <td>1528905498</td>
                  <td>69</td>
                  <td>57.32</td>
                  <td>43.11</td>
                  <td>60.70</td>
                  <td>15.03</td>
                </tr>
                <tr>
                  <td>343</td>
                  <td>bundaberg</td>
                  <td>88</td>
                  <td>AU</td>
                  <td>1528905498</td>
                  <td>100</td>
                  <td>-24.87</td>
                  <td>152.35</td>
                  <td>64.66</td>
                  <td>12.01</td>
                </tr>
                <tr>
                  <td>344</td>
                  <td>griffith</td>
                  <td>80</td>
                  <td>AU</td>
                  <td>1528905499</td>
                  <td>90</td>
                  <td>-34.29</td>
                  <td>146.06</td>
                  <td>50.62</td>
                  <td>8.88</td>
                </tr>
                <tr>
                  <td>345</td>
                  <td>raudeberg</td>
                  <td>75</td>
                  <td>NO</td>
                  <td>1528903200</td>
                  <td>71</td>
                  <td>61.99</td>
                  <td>5.14</td>
                  <td>60.80</td>
                  <td>11.41</td>
                </tr>
                <tr>
                  <td>346</td>
                  <td>rio gallegos</td>
                  <td>20</td>
                  <td>AR</td>
                  <td>1528902000</td>
                  <td>86</td>
                  <td>-51.62</td>
                  <td>-69.22</td>
                  <td>33.80</td>
                  <td>5.82</td>
                </tr>
                <tr>
                  <td>347</td>
                  <td>antalaha</td>
                  <td>88</td>
                  <td>MG</td>
                  <td>1528905500</td>
                  <td>85</td>
                  <td>-14.90</td>
                  <td>50.28</td>
                  <td>75.01</td>
                  <td>14.14</td>
                </tr>
                <tr>
                  <td>348</td>
                  <td>houma</td>
                  <td>0</td>
                  <td>CN</td>
                  <td>1528905500</td>
                  <td>58</td>
                  <td>35.63</td>
                  <td>111.36</td>
                  <td>62.32</td>
                  <td>2.51</td>
                </tr>
                <tr>
                  <td>349</td>
                  <td>verkhoyansk</td>
                  <td>0</td>
                  <td>RU</td>
                  <td>1528905500</td>
                  <td>63</td>
                  <td>67.55</td>
                  <td>133.39</td>
                  <td>56.29</td>
                  <td>2.62</td>
                </tr>
                <tr>
                  <td>350</td>
                  <td>donskoye</td>
                  <td>0</td>
                  <td>RU</td>
                  <td>1528902000</td>
                  <td>30</td>
                  <td>45.45</td>
                  <td>41.98</td>
                  <td>80.60</td>
                  <td>6.71</td>
                </tr>
                <tr>
                  <td>351</td>
                  <td>mogadishu</td>
                  <td>64</td>
                  <td>SO</td>
                  <td>1528905402</td>
                  <td>100</td>
                  <td>2.04</td>
                  <td>45.34</td>
                  <td>78.25</td>
                  <td>22.08</td>
                </tr>
                <tr>
                  <td>352</td>
                  <td>lewistown</td>
                  <td>1</td>
                  <td>US</td>
                  <td>1528904100</td>
                  <td>53</td>
                  <td>40.39</td>
                  <td>-90.15</td>
                  <td>78.80</td>
                  <td>12.75</td>
                </tr>
                <tr>
                  <td>353</td>
                  <td>leningradskiy</td>
                  <td>0</td>
                  <td>RU</td>
                  <td>1528905501</td>
                  <td>88</td>
                  <td>69.38</td>
                  <td>178.42</td>
                  <td>33.79</td>
                  <td>21.74</td>
                </tr>
                <tr>
                  <td>354</td>
                  <td>airai</td>
                  <td>76</td>
                  <td>TL</td>
                  <td>1528905503</td>
                  <td>93</td>
                  <td>-8.93</td>
                  <td>125.41</td>
                  <td>68.98</td>
                  <td>1.72</td>
                </tr>
                <tr>
                  <td>355</td>
                  <td>nantucket</td>
                  <td>90</td>
                  <td>US</td>
                  <td>1528904100</td>
                  <td>77</td>
                  <td>41.28</td>
                  <td>-70.10</td>
                  <td>69.80</td>
                  <td>17.22</td>
                </tr>
                <tr>
                  <td>356</td>
                  <td>mount gambier</td>
                  <td>92</td>
                  <td>AU</td>
                  <td>1528905506</td>
                  <td>81</td>
                  <td>-37.83</td>
                  <td>140.78</td>
                  <td>49.72</td>
                  <td>6.87</td>
                </tr>
                <tr>
                  <td>357</td>
                  <td>katobu</td>
                  <td>24</td>
                  <td>ID</td>
                  <td>1528905506</td>
                  <td>100</td>
                  <td>-4.94</td>
                  <td>122.53</td>
                  <td>77.98</td>
                  <td>2.62</td>
                </tr>
                <tr>
                  <td>358</td>
                  <td>baiyin</td>
                  <td>0</td>
                  <td>CN</td>
                  <td>1528902000</td>
                  <td>31</td>
                  <td>36.55</td>
                  <td>104.13</td>
                  <td>60.80</td>
                  <td>4.47</td>
                </tr>
                <tr>
                  <td>359</td>
                  <td>jumla</td>
                  <td>88</td>
                  <td>NP</td>
                  <td>1528905507</td>
                  <td>95</td>
                  <td>29.28</td>
                  <td>82.18</td>
                  <td>37.75</td>
                  <td>2.51</td>
                </tr>
                <tr>
                  <td>360</td>
                  <td>voh</td>
                  <td>8</td>
                  <td>NC</td>
                  <td>1528905507</td>
                  <td>100</td>
                  <td>-20.95</td>
                  <td>164.69</td>
                  <td>71.59</td>
                  <td>14.81</td>
                </tr>
                <tr>
                  <td>361</td>
                  <td>kamaishi</td>
                  <td>0</td>
                  <td>JP</td>
                  <td>1528905507</td>
                  <td>78</td>
                  <td>39.28</td>
                  <td>141.86</td>
                  <td>53.95</td>
                  <td>12.80</td>
                </tr>
                <tr>
                  <td>362</td>
                  <td>jurm</td>
                  <td>56</td>
                  <td>AF</td>
                  <td>1528905508</td>
                  <td>100</td>
                  <td>36.86</td>
                  <td>70.83</td>
                  <td>40.09</td>
                  <td>1.61</td>
                </tr>
                <tr>
                  <td>363</td>
                  <td>la ronge</td>
                  <td>75</td>
                  <td>CA</td>
                  <td>1528902000</td>
                  <td>76</td>
                  <td>55.10</td>
                  <td>-105.30</td>
                  <td>53.60</td>
                  <td>8.05</td>
                </tr>
                <tr>
                  <td>364</td>
                  <td>paragominas</td>
                  <td>20</td>
                  <td>BR</td>
                  <td>1528905508</td>
                  <td>56</td>
                  <td>-3.00</td>
                  <td>-47.35</td>
                  <td>91.93</td>
                  <td>5.41</td>
                </tr>
                <tr>
                  <td>365</td>
                  <td>fairbanks</td>
                  <td>1</td>
                  <td>US</td>
                  <td>1528901880</td>
                  <td>75</td>
                  <td>64.84</td>
                  <td>-147.72</td>
                  <td>42.80</td>
                  <td>3.36</td>
                </tr>
                <tr>
                  <td>366</td>
                  <td>poum</td>
                  <td>40</td>
                  <td>MK</td>
                  <td>1528903800</td>
                  <td>47</td>
                  <td>41.28</td>
                  <td>20.71</td>
                  <td>78.80</td>
                  <td>8.05</td>
                </tr>
                <tr>
                  <td>367</td>
                  <td>boyle</td>
                  <td>75</td>
                  <td>IE</td>
                  <td>1528902000</td>
                  <td>100</td>
                  <td>53.97</td>
                  <td>-8.30</td>
                  <td>55.40</td>
                  <td>18.34</td>
                </tr>
                <tr>
                  <td>368</td>
                  <td>klaksvik</td>
                  <td>92</td>
                  <td>FO</td>
                  <td>1528903200</td>
                  <td>93</td>
                  <td>62.23</td>
                  <td>-6.59</td>
                  <td>48.20</td>
                  <td>19.46</td>
                </tr>
                <tr>
                  <td>369</td>
                  <td>aleksandro-nevskiy</td>
                  <td>0</td>
                  <td>RU</td>
                  <td>1528905510</td>
                  <td>49</td>
                  <td>53.48</td>
                  <td>40.21</td>
                  <td>74.20</td>
                  <td>9.78</td>
                </tr>
                <tr>
                  <td>370</td>
                  <td>graham</td>
                  <td>75</td>
                  <td>US</td>
                  <td>1528905240</td>
                  <td>78</td>
                  <td>36.07</td>
                  <td>-79.40</td>
                  <td>75.20</td>
                  <td>9.17</td>
                </tr>
                <tr>
                  <td>371</td>
                  <td>paraiso</td>
                  <td>75</td>
                  <td>MX</td>
                  <td>1528901040</td>
                  <td>68</td>
                  <td>24.01</td>
                  <td>-104.61</td>
                  <td>66.20</td>
                  <td>3.36</td>
                </tr>
                <tr>
                  <td>372</td>
                  <td>nishihara</td>
                  <td>75</td>
                  <td>JP</td>
                  <td>1528902000</td>
                  <td>68</td>
                  <td>35.74</td>
                  <td>139.53</td>
                  <td>69.80</td>
                  <td>3.36</td>
                </tr>
                <tr>
                  <td>373</td>
                  <td>charyshskoye</td>
                  <td>8</td>
                  <td>RU</td>
                  <td>1528905511</td>
                  <td>37</td>
                  <td>51.40</td>
                  <td>83.56</td>
                  <td>69.70</td>
                  <td>3.40</td>
                </tr>
                <tr>
                  <td>374</td>
                  <td>struer</td>
                  <td>8</td>
                  <td>DK</td>
                  <td>1528903200</td>
                  <td>63</td>
                  <td>56.48</td>
                  <td>8.60</td>
                  <td>60.80</td>
                  <td>17.22</td>
                </tr>
                <tr>
                  <td>375</td>
                  <td>hualmay</td>
                  <td>12</td>
                  <td>PE</td>
                  <td>1528905511</td>
                  <td>77</td>
                  <td>-11.10</td>
                  <td>-77.61</td>
                  <td>65.02</td>
                  <td>3.62</td>
                </tr>
                <tr>
                  <td>376</td>
                  <td>ystad</td>
                  <td>75</td>
                  <td>SE</td>
                  <td>1528903200</td>
                  <td>60</td>
                  <td>55.43</td>
                  <td>13.82</td>
                  <td>68.00</td>
                  <td>13.87</td>
                </tr>
                <tr>
                  <td>377</td>
                  <td>buin</td>
                  <td>0</td>
                  <td>CL</td>
                  <td>1528905600</td>
                  <td>65</td>
                  <td>-33.73</td>
                  <td>-70.74</td>
                  <td>46.40</td>
                  <td>3.36</td>
                </tr>
                <tr>
                  <td>378</td>
                  <td>gamboma</td>
                  <td>0</td>
                  <td>CG</td>
                  <td>1528905516</td>
                  <td>64</td>
                  <td>-1.87</td>
                  <td>15.88</td>
                  <td>87.34</td>
                  <td>6.53</td>
                </tr>
                <tr>
                  <td>379</td>
                  <td>bristol</td>
                  <td>75</td>
                  <td>GB</td>
                  <td>1528903200</td>
                  <td>77</td>
                  <td>51.45</td>
                  <td>-2.60</td>
                  <td>68.00</td>
                  <td>10.29</td>
                </tr>
                <tr>
                  <td>380</td>
                  <td>imbituba</td>
                  <td>40</td>
                  <td>BR</td>
                  <td>1528902000</td>
                  <td>64</td>
                  <td>-28.24</td>
                  <td>-48.67</td>
                  <td>69.80</td>
                  <td>3.36</td>
                </tr>
                <tr>
                  <td>381</td>
                  <td>comrie</td>
                  <td>40</td>
                  <td>GB</td>
                  <td>1528903200</td>
                  <td>72</td>
                  <td>56.09</td>
                  <td>-3.58</td>
                  <td>60.80</td>
                  <td>14.99</td>
                </tr>
                <tr>
                  <td>382</td>
                  <td>esil</td>
                  <td>0</td>
                  <td>KZ</td>
                  <td>1528905517</td>
                  <td>50</td>
                  <td>51.96</td>
                  <td>66.41</td>
                  <td>60.25</td>
                  <td>7.65</td>
                </tr>
                <tr>
                  <td>383</td>
                  <td>lompoc</td>
                  <td>1</td>
                  <td>US</td>
                  <td>1528904100</td>
                  <td>63</td>
                  <td>34.64</td>
                  <td>-120.46</td>
                  <td>62.60</td>
                  <td>2.51</td>
                </tr>
                <tr>
                  <td>384</td>
                  <td>coihaique</td>
                  <td>80</td>
                  <td>CL</td>
                  <td>1528902000</td>
                  <td>85</td>
                  <td>-45.58</td>
                  <td>-72.07</td>
                  <td>33.80</td>
                  <td>2.24</td>
                </tr>
                <tr>
                  <td>385</td>
                  <td>hamilton</td>
                  <td>40</td>
                  <td>BM</td>
                  <td>1528901700</td>
                  <td>73</td>
                  <td>32.30</td>
                  <td>-64.78</td>
                  <td>77.00</td>
                  <td>10.29</td>
                </tr>
                <tr>
                  <td>386</td>
                  <td>hasaki</td>
                  <td>75</td>
                  <td>JP</td>
                  <td>1528902000</td>
                  <td>93</td>
                  <td>35.73</td>
                  <td>140.83</td>
                  <td>64.40</td>
                  <td>3.36</td>
                </tr>
                <tr>
                  <td>387</td>
                  <td>kajaani</td>
                  <td>0</td>
                  <td>FI</td>
                  <td>1528903200</td>
                  <td>52</td>
                  <td>64.22</td>
                  <td>27.73</td>
                  <td>53.60</td>
                  <td>4.70</td>
                </tr>
                <tr>
                  <td>388</td>
                  <td>tupik</td>
                  <td>0</td>
                  <td>RU</td>
                  <td>1528905520</td>
                  <td>63</td>
                  <td>54.43</td>
                  <td>119.94</td>
                  <td>51.25</td>
                  <td>4.63</td>
                </tr>
                <tr>
                  <td>389</td>
                  <td>kloulklubed</td>
                  <td>90</td>
                  <td>PW</td>
                  <td>1528901700</td>
                  <td>83</td>
                  <td>7.04</td>
                  <td>134.26</td>
                  <td>82.40</td>
                  <td>9.17</td>
                </tr>
                <tr>
                  <td>390</td>
                  <td>kieta</td>
                  <td>32</td>
                  <td>PG</td>
                  <td>1528905520</td>
                  <td>100</td>
                  <td>-6.22</td>
                  <td>155.63</td>
                  <td>76.81</td>
                  <td>2.73</td>
                </tr>
                <tr>
                  <td>391</td>
                  <td>maldonado</td>
                  <td>75</td>
                  <td>UY</td>
                  <td>1528902000</td>
                  <td>76</td>
                  <td>-34.91</td>
                  <td>-54.96</td>
                  <td>51.80</td>
                  <td>19.46</td>
                </tr>
                <tr>
                  <td>392</td>
                  <td>smithers</td>
                  <td>75</td>
                  <td>CA</td>
                  <td>1528902000</td>
                  <td>81</td>
                  <td>54.78</td>
                  <td>-127.17</td>
                  <td>48.20</td>
                  <td>2.62</td>
                </tr>
                <tr>
                  <td>393</td>
                  <td>mareeba</td>
                  <td>0</td>
                  <td>AU</td>
                  <td>1528902000</td>
                  <td>93</td>
                  <td>-16.99</td>
                  <td>145.42</td>
                  <td>60.80</td>
                  <td>3.40</td>
                </tr>
                <tr>
                  <td>394</td>
                  <td>kaputa</td>
                  <td>0</td>
                  <td>ZM</td>
                  <td>1528905521</td>
                  <td>29</td>
                  <td>-8.47</td>
                  <td>29.66</td>
                  <td>78.88</td>
                  <td>3.62</td>
                </tr>
                <tr>
                  <td>395</td>
                  <td>lira</td>
                  <td>68</td>
                  <td>UG</td>
                  <td>1528905521</td>
                  <td>45</td>
                  <td>2.25</td>
                  <td>32.90</td>
                  <td>82.39</td>
                  <td>8.21</td>
                </tr>
                <tr>
                  <td>396</td>
                  <td>constitucion</td>
                  <td>75</td>
                  <td>MX</td>
                  <td>1528901040</td>
                  <td>68</td>
                  <td>23.99</td>
                  <td>-104.67</td>
                  <td>66.20</td>
                  <td>3.36</td>
                </tr>
                <tr>
                  <td>397</td>
                  <td>ternate</td>
                  <td>90</td>
                  <td>PH</td>
                  <td>1528902000</td>
                  <td>100</td>
                  <td>14.29</td>
                  <td>120.72</td>
                  <td>77.00</td>
                  <td>10.29</td>
                </tr>
                <tr>
                  <td>398</td>
                  <td>haines junction</td>
                  <td>68</td>
                  <td>CA</td>
                  <td>1528905526</td>
                  <td>52</td>
                  <td>60.75</td>
                  <td>-137.51</td>
                  <td>42.79</td>
                  <td>2.62</td>
                </tr>
                <tr>
                  <td>399</td>
                  <td>zagora</td>
                  <td>75</td>
                  <td>HR</td>
                  <td>1528903800</td>
                  <td>73</td>
                  <td>46.19</td>
                  <td>15.87</td>
                  <td>71.60</td>
                  <td>2.24</td>
                </tr>
                <tr>
                  <td>400</td>
                  <td>zhongxing</td>
                  <td>8</td>
                  <td>CN</td>
                  <td>1528905527</td>
                  <td>69</td>
                  <td>32.02</td>
                  <td>116.14</td>
                  <td>74.29</td>
                  <td>7.99</td>
                </tr>
                <tr>
                  <td>401</td>
                  <td>snezhnogorsk</td>
                  <td>75</td>
                  <td>RU</td>
                  <td>1528903800</td>
                  <td>70</td>
                  <td>69.19</td>
                  <td>33.23</td>
                  <td>42.80</td>
                  <td>2.24</td>
                </tr>
                <tr>
                  <td>402</td>
                  <td>sola</td>
                  <td>75</td>
                  <td>FI</td>
                  <td>1528903200</td>
                  <td>76</td>
                  <td>62.78</td>
                  <td>29.36</td>
                  <td>50.00</td>
                  <td>10.29</td>
                </tr>
                <tr>
                  <td>403</td>
                  <td>sioux lookout</td>
                  <td>20</td>
                  <td>CA</td>
                  <td>1528902000</td>
                  <td>59</td>
                  <td>50.10</td>
                  <td>-91.92</td>
                  <td>66.20</td>
                  <td>4.70</td>
                </tr>
                <tr>
                  <td>404</td>
                  <td>sur</td>
                  <td>0</td>
                  <td>OM</td>
                  <td>1528905530</td>
                  <td>82</td>
                  <td>22.57</td>
                  <td>59.53</td>
                  <td>89.32</td>
                  <td>4.85</td>
                </tr>
                <tr>
                  <td>405</td>
                  <td>utete</td>
                  <td>12</td>
                  <td>TZ</td>
                  <td>1528905531</td>
                  <td>51</td>
                  <td>-7.99</td>
                  <td>38.76</td>
                  <td>81.76</td>
                  <td>6.08</td>
                </tr>
                <tr>
                  <td>406</td>
                  <td>saint-joseph</td>
                  <td>75</td>
                  <td>FR</td>
                  <td>1528903800</td>
                  <td>60</td>
                  <td>43.56</td>
                  <td>6.97</td>
                  <td>71.60</td>
                  <td>4.70</td>
                </tr>
                <tr>
                  <td>407</td>
                  <td>sadao</td>
                  <td>75</td>
                  <td>TH</td>
                  <td>1528902000</td>
                  <td>83</td>
                  <td>6.63</td>
                  <td>100.42</td>
                  <td>82.40</td>
                  <td>2.24</td>
                </tr>
                <tr>
                  <td>408</td>
                  <td>petropavlovsk-kamchatskiy</td>
                  <td>90</td>
                  <td>RU</td>
                  <td>1528902000</td>
                  <td>86</td>
                  <td>53.05</td>
                  <td>158.65</td>
                  <td>41.00</td>
                  <td>2.24</td>
                </tr>
                <tr>
                  <td>409</td>
                  <td>vestmanna</td>
                  <td>92</td>
                  <td>FO</td>
                  <td>1528903200</td>
                  <td>93</td>
                  <td>62.16</td>
                  <td>-7.17</td>
                  <td>48.20</td>
                  <td>19.46</td>
                </tr>
                <tr>
                  <td>410</td>
                  <td>chifeng</td>
                  <td>8</td>
                  <td>CN</td>
                  <td>1528905536</td>
                  <td>90</td>
                  <td>42.27</td>
                  <td>118.96</td>
                  <td>52.42</td>
                  <td>0.72</td>
                </tr>
                <tr>
                  <td>411</td>
                  <td>grants pass</td>
                  <td>90</td>
                  <td>US</td>
                  <td>1528901760</td>
                  <td>50</td>
                  <td>42.44</td>
                  <td>-123.33</td>
                  <td>59.00</td>
                  <td>2.62</td>
                </tr>
                <tr>
                  <td>412</td>
                  <td>lampazos de naranjo</td>
                  <td>0</td>
                  <td>MX</td>
                  <td>1528905536</td>
                  <td>57</td>
                  <td>27.02</td>
                  <td>-100.51</td>
                  <td>82.93</td>
                  <td>6.76</td>
                </tr>
                <tr>
                  <td>413</td>
                  <td>salym</td>
                  <td>48</td>
                  <td>RU</td>
                  <td>1528905536</td>
                  <td>51</td>
                  <td>60.06</td>
                  <td>71.48</td>
                  <td>60.61</td>
                  <td>5.08</td>
                </tr>
                <tr>
                  <td>414</td>
                  <td>verkh-chebula</td>
                  <td>0</td>
                  <td>RU</td>
                  <td>1528905536</td>
                  <td>75</td>
                  <td>56.03</td>
                  <td>87.61</td>
                  <td>67.36</td>
                  <td>2.73</td>
                </tr>
                <tr>
                  <td>415</td>
                  <td>tsiroanomandidy</td>
                  <td>64</td>
                  <td>MG</td>
                  <td>1528905537</td>
                  <td>36</td>
                  <td>-18.77</td>
                  <td>46.05</td>
                  <td>71.86</td>
                  <td>4.97</td>
                </tr>
                <tr>
                  <td>416</td>
                  <td>lagoa</td>
                  <td>20</td>
                  <td>PT</td>
                  <td>1528903800</td>
                  <td>56</td>
                  <td>37.14</td>
                  <td>-8.45</td>
                  <td>71.60</td>
                  <td>10.29</td>
                </tr>
                <tr>
                  <td>417</td>
                  <td>les cayes</td>
                  <td>88</td>
                  <td>HT</td>
                  <td>1528905538</td>
                  <td>92</td>
                  <td>18.19</td>
                  <td>-73.75</td>
                  <td>82.93</td>
                  <td>22.41</td>
                </tr>
                <tr>
                  <td>418</td>
                  <td>mackay</td>
                  <td>75</td>
                  <td>CA</td>
                  <td>1528902000</td>
                  <td>81</td>
                  <td>53.65</td>
                  <td>-115.58</td>
                  <td>50.00</td>
                  <td>3.36</td>
                </tr>
                <tr>
                  <td>419</td>
                  <td>treuchtlingen</td>
                  <td>75</td>
                  <td>DE</td>
                  <td>1528903200</td>
                  <td>67</td>
                  <td>48.96</td>
                  <td>10.91</td>
                  <td>60.80</td>
                  <td>8.05</td>
                </tr>
                <tr>
                  <td>420</td>
                  <td>witney</td>
                  <td>40</td>
                  <td>GB</td>
                  <td>1528903200</td>
                  <td>56</td>
                  <td>51.78</td>
                  <td>-1.49</td>
                  <td>69.80</td>
                  <td>16.11</td>
                </tr>
                <tr>
                  <td>421</td>
                  <td>tabou</td>
                  <td>0</td>
                  <td>CI</td>
                  <td>1528905538</td>
                  <td>100</td>
                  <td>4.42</td>
                  <td>-7.36</td>
                  <td>80.86</td>
                  <td>9.78</td>
                </tr>
                <tr>
                  <td>422</td>
                  <td>koson</td>
                  <td>0</td>
                  <td>UZ</td>
                  <td>1528902000</td>
                  <td>19</td>
                  <td>39.04</td>
                  <td>65.59</td>
                  <td>89.60</td>
                  <td>9.17</td>
                </tr>
                <tr>
                  <td>423</td>
                  <td>burewala</td>
                  <td>0</td>
                  <td>PK</td>
                  <td>1528905539</td>
                  <td>34</td>
                  <td>30.16</td>
                  <td>72.68</td>
                  <td>95.62</td>
                  <td>7.20</td>
                </tr>
                <tr>
                  <td>424</td>
                  <td>aksum</td>
                  <td>80</td>
                  <td>ET</td>
                  <td>1528905539</td>
                  <td>94</td>
                  <td>14.12</td>
                  <td>38.72</td>
                  <td>61.15</td>
                  <td>3.40</td>
                </tr>
                <tr>
                  <td>425</td>
                  <td>iquitos</td>
                  <td>20</td>
                  <td>PE</td>
                  <td>1528902000</td>
                  <td>74</td>
                  <td>-3.75</td>
                  <td>-73.25</td>
                  <td>84.20</td>
                  <td>4.70</td>
                </tr>
                <tr>
                  <td>426</td>
                  <td>bealanana</td>
                  <td>20</td>
                  <td>MG</td>
                  <td>1528905541</td>
                  <td>53</td>
                  <td>-14.54</td>
                  <td>48.75</td>
                  <td>69.07</td>
                  <td>6.98</td>
                </tr>
                <tr>
                  <td>427</td>
                  <td>linqiong</td>
                  <td>92</td>
                  <td>CN</td>
                  <td>1528902000</td>
                  <td>83</td>
                  <td>30.42</td>
                  <td>103.46</td>
                  <td>75.20</td>
                  <td>6.71</td>
                </tr>
                <tr>
                  <td>428</td>
                  <td>bonaventure</td>
                  <td>75</td>
                  <td>CA</td>
                  <td>1528902000</td>
                  <td>32</td>
                  <td>48.04</td>
                  <td>-65.49</td>
                  <td>66.20</td>
                  <td>8.05</td>
                </tr>
                <tr>
                  <td>429</td>
                  <td>ostrovnoy</td>
                  <td>92</td>
                  <td>RU</td>
                  <td>1528905546</td>
                  <td>82</td>
                  <td>68.05</td>
                  <td>39.51</td>
                  <td>36.58</td>
                  <td>18.28</td>
                </tr>
                <tr>
                  <td>430</td>
                  <td>narsaq</td>
                  <td>40</td>
                  <td>GL</td>
                  <td>1528905000</td>
                  <td>43</td>
                  <td>60.91</td>
                  <td>-46.05</td>
                  <td>55.40</td>
                  <td>9.17</td>
                </tr>
                <tr>
                  <td>431</td>
                  <td>richards bay</td>
                  <td>0</td>
                  <td>ZA</td>
                  <td>1528905547</td>
                  <td>75</td>
                  <td>-28.77</td>
                  <td>32.06</td>
                  <td>68.53</td>
                  <td>1.72</td>
                </tr>
                <tr>
                  <td>432</td>
                  <td>antofagasta</td>
                  <td>40</td>
                  <td>CL</td>
                  <td>1528902000</td>
                  <td>67</td>
                  <td>-23.65</td>
                  <td>-70.40</td>
                  <td>57.20</td>
                  <td>8.05</td>
                </tr>
                <tr>
                  <td>433</td>
                  <td>yeniseysk</td>
                  <td>8</td>
                  <td>RU</td>
                  <td>1528905547</td>
                  <td>71</td>
                  <td>58.45</td>
                  <td>92.17</td>
                  <td>63.49</td>
                  <td>2.84</td>
                </tr>
                <tr>
                  <td>434</td>
                  <td>taguatinga</td>
                  <td>20</td>
                  <td>BR</td>
                  <td>1528902000</td>
                  <td>36</td>
                  <td>-15.83</td>
                  <td>-48.06</td>
                  <td>78.80</td>
                  <td>5.82</td>
                </tr>
                <tr>
                  <td>435</td>
                  <td>port-gentil</td>
                  <td>20</td>
                  <td>GA</td>
                  <td>1528902000</td>
                  <td>78</td>
                  <td>-0.72</td>
                  <td>8.78</td>
                  <td>82.40</td>
                  <td>16.11</td>
                </tr>
                <tr>
                  <td>436</td>
                  <td>yulara</td>
                  <td>0</td>
                  <td>AU</td>
                  <td>1528902000</td>
                  <td>56</td>
                  <td>-25.24</td>
                  <td>130.99</td>
                  <td>41.00</td>
                  <td>4.70</td>
                </tr>
                <tr>
                  <td>437</td>
                  <td>adrar</td>
                  <td>0</td>
                  <td>DZ</td>
                  <td>1528902000</td>
                  <td>12</td>
                  <td>27.87</td>
                  <td>-0.29</td>
                  <td>109.40</td>
                  <td>11.41</td>
                </tr>
                <tr>
                  <td>438</td>
                  <td>samur</td>
                  <td>0</td>
                  <td>RU</td>
                  <td>1528905549</td>
                  <td>84</td>
                  <td>41.83</td>
                  <td>48.49</td>
                  <td>71.23</td>
                  <td>13.13</td>
                </tr>
                <tr>
                  <td>439</td>
                  <td>chicla</td>
                  <td>20</td>
                  <td>PE</td>
                  <td>1528905550</td>
                  <td>74</td>
                  <td>-11.71</td>
                  <td>-76.27</td>
                  <td>43.69</td>
                  <td>2.39</td>
                </tr>
                <tr>
                  <td>440</td>
                  <td>tombouctou</td>
                  <td>24</td>
                  <td>ML</td>
                  <td>1528905550</td>
                  <td>18</td>
                  <td>16.77</td>
                  <td>-3.01</td>
                  <td>110.65</td>
                  <td>4.74</td>
                </tr>
                <tr>
                  <td>441</td>
                  <td>pyaozerskiy</td>
                  <td>48</td>
                  <td>RU</td>
                  <td>1528905550</td>
                  <td>57</td>
                  <td>65.83</td>
                  <td>31.17</td>
                  <td>49.00</td>
                  <td>3.96</td>
                </tr>
                <tr>
                  <td>442</td>
                  <td>vagur</td>
                  <td>92</td>
                  <td>FO</td>
                  <td>1528905550</td>
                  <td>97</td>
                  <td>61.47</td>
                  <td>-6.81</td>
                  <td>49.63</td>
                  <td>27.89</td>
                </tr>
                <tr>
                  <td>443</td>
                  <td>yar-sale</td>
                  <td>76</td>
                  <td>RU</td>
                  <td>1528905551</td>
                  <td>89</td>
                  <td>66.83</td>
                  <td>70.83</td>
                  <td>36.22</td>
                  <td>14.81</td>
                </tr>
                <tr>
                  <td>444</td>
                  <td>ust-nera</td>
                  <td>48</td>
                  <td>RU</td>
                  <td>1528905551</td>
                  <td>65</td>
                  <td>64.57</td>
                  <td>143.24</td>
                  <td>46.93</td>
                  <td>1.72</td>
                </tr>
                <tr>
                  <td>445</td>
                  <td>solnechnyy</td>
                  <td>0</td>
                  <td>RU</td>
                  <td>1528905551</td>
                  <td>78</td>
                  <td>50.72</td>
                  <td>136.64</td>
                  <td>51.52</td>
                  <td>4.18</td>
                </tr>
                <tr>
                  <td>446</td>
                  <td>san patricio</td>
                  <td>0</td>
                  <td>PY</td>
                  <td>1528905551</td>
                  <td>74</td>
                  <td>-26.98</td>
                  <td>-56.83</td>
                  <td>51.79</td>
                  <td>4.63</td>
                </tr>
                <tr>
                  <td>447</td>
                  <td>angoram</td>
                  <td>88</td>
                  <td>PG</td>
                  <td>1528905555</td>
                  <td>100</td>
                  <td>-4.06</td>
                  <td>144.07</td>
                  <td>74.47</td>
                  <td>1.95</td>
                </tr>
                <tr>
                  <td>448</td>
                  <td>champerico</td>
                  <td>90</td>
                  <td>MX</td>
                  <td>1528900860</td>
                  <td>94</td>
                  <td>16.38</td>
                  <td>-93.60</td>
                  <td>71.60</td>
                  <td>2.62</td>
                </tr>
                <tr>
                  <td>449</td>
                  <td>san policarpo</td>
                  <td>80</td>
                  <td>PH</td>
                  <td>1528905556</td>
                  <td>100</td>
                  <td>12.18</td>
                  <td>125.51</td>
                  <td>78.43</td>
                  <td>7.76</td>
                </tr>
                <tr>
                  <td>450</td>
                  <td>port-cartier</td>
                  <td>40</td>
                  <td>CA</td>
                  <td>1528902000</td>
                  <td>47</td>
                  <td>50.03</td>
                  <td>-66.88</td>
                  <td>55.40</td>
                  <td>16.11</td>
                </tr>
                <tr>
                  <td>451</td>
                  <td>tateyama</td>
                  <td>12</td>
                  <td>JP</td>
                  <td>1528905556</td>
                  <td>100</td>
                  <td>36.66</td>
                  <td>137.31</td>
                  <td>49.45</td>
                  <td>1.95</td>
                </tr>
                <tr>
                  <td>452</td>
                  <td>mandalgovi</td>
                  <td>8</td>
                  <td>MN</td>
                  <td>1528905556</td>
                  <td>35</td>
                  <td>45.76</td>
                  <td>106.27</td>
                  <td>62.59</td>
                  <td>6.64</td>
                </tr>
                <tr>
                  <td>453</td>
                  <td>bartica</td>
                  <td>75</td>
                  <td>GY</td>
                  <td>1528902000</td>
                  <td>78</td>
                  <td>6.41</td>
                  <td>-58.62</td>
                  <td>82.40</td>
                  <td>9.17</td>
                </tr>
                <tr>
                  <td>454</td>
                  <td>bathsheba</td>
                  <td>20</td>
                  <td>BB</td>
                  <td>1528902000</td>
                  <td>66</td>
                  <td>13.22</td>
                  <td>-59.52</td>
                  <td>86.00</td>
                  <td>25.28</td>
                </tr>
                <tr>
                  <td>455</td>
                  <td>bueu</td>
                  <td>0</td>
                  <td>ES</td>
                  <td>1528903800</td>
                  <td>53</td>
                  <td>42.33</td>
                  <td>-8.79</td>
                  <td>71.60</td>
                  <td>16.11</td>
                </tr>
                <tr>
                  <td>456</td>
                  <td>chaltyr</td>
                  <td>0</td>
                  <td>RU</td>
                  <td>1528905557</td>
                  <td>21</td>
                  <td>47.28</td>
                  <td>39.48</td>
                  <td>87.43</td>
                  <td>3.74</td>
                </tr>
                <tr>
                  <td>457</td>
                  <td>prince rupert</td>
                  <td>90</td>
                  <td>CA</td>
                  <td>1528902000</td>
                  <td>93</td>
                  <td>54.32</td>
                  <td>-130.32</td>
                  <td>53.60</td>
                  <td>6.93</td>
                </tr>
                <tr>
                  <td>458</td>
                  <td>plouzane</td>
                  <td>90</td>
                  <td>FR</td>
                  <td>1528903800</td>
                  <td>63</td>
                  <td>48.38</td>
                  <td>-4.62</td>
                  <td>66.20</td>
                  <td>8.05</td>
                </tr>
                <tr>
                  <td>459</td>
                  <td>belaya gora</td>
                  <td>36</td>
                  <td>RU</td>
                  <td>1528905558</td>
                  <td>35</td>
                  <td>68.54</td>
                  <td>146.19</td>
                  <td>62.77</td>
                  <td>4.07</td>
                </tr>
                <tr>
                  <td>460</td>
                  <td>tongren</td>
                  <td>12</td>
                  <td>CN</td>
                  <td>1528905558</td>
                  <td>85</td>
                  <td>27.72</td>
                  <td>109.18</td>
                  <td>67.90</td>
                  <td>1.95</td>
                </tr>
                <tr>
                  <td>461</td>
                  <td>narsimhapur</td>
                  <td>88</td>
                  <td>IN</td>
                  <td>1528905558</td>
                  <td>78</td>
                  <td>17.14</td>
                  <td>74.26</td>
                  <td>76.00</td>
                  <td>9.22</td>
                </tr>
                <tr>
                  <td>462</td>
                  <td>sao joao da barra</td>
                  <td>0</td>
                  <td>BR</td>
                  <td>1528902000</td>
                  <td>43</td>
                  <td>-21.64</td>
                  <td>-41.05</td>
                  <td>87.80</td>
                  <td>5.82</td>
                </tr>
                <tr>
                  <td>463</td>
                  <td>mamakan</td>
                  <td>32</td>
                  <td>RU</td>
                  <td>1528905559</td>
                  <td>83</td>
                  <td>57.82</td>
                  <td>114.02</td>
                  <td>51.70</td>
                  <td>2.06</td>
                </tr>
                <tr>
                  <td>464</td>
                  <td>inirida</td>
                  <td>80</td>
                  <td>CO</td>
                  <td>1528905559</td>
                  <td>84</td>
                  <td>3.87</td>
                  <td>-67.92</td>
                  <td>80.32</td>
                  <td>2.95</td>
                </tr>
                <tr>
                  <td>465</td>
                  <td>payo</td>
                  <td>56</td>
                  <td>ID</td>
                  <td>1528905559</td>
                  <td>84</td>
                  <td>-3.75</td>
                  <td>103.64</td>
                  <td>77.98</td>
                  <td>4.74</td>
                </tr>
                <tr>
                  <td>466</td>
                  <td>san carlos de bariloche</td>
                  <td>75</td>
                  <td>AR</td>
                  <td>1528902000</td>
                  <td>86</td>
                  <td>-41.13</td>
                  <td>-71.31</td>
                  <td>26.60</td>
                  <td>10.29</td>
                </tr>
                <tr>
                  <td>467</td>
                  <td>piacabucu</td>
                  <td>44</td>
                  <td>BR</td>
                  <td>1528905560</td>
                  <td>57</td>
                  <td>-10.41</td>
                  <td>-36.43</td>
                  <td>84.37</td>
                  <td>15.48</td>
                </tr>
                <tr>
                  <td>468</td>
                  <td>auki</td>
                  <td>44</td>
                  <td>NG</td>
                  <td>1528905560</td>
                  <td>55</td>
                  <td>12.18</td>
                  <td>6.51</td>
                  <td>94.81</td>
                  <td>1.61</td>
                </tr>
                <tr>
                  <td>469</td>
                  <td>ambon</td>
                  <td>90</td>
                  <td>FR</td>
                  <td>1528903800</td>
                  <td>64</td>
                  <td>47.55</td>
                  <td>-2.56</td>
                  <td>69.80</td>
                  <td>8.05</td>
                </tr>
                <tr>
                  <td>470</td>
                  <td>bilibino</td>
                  <td>0</td>
                  <td>RU</td>
                  <td>1528905560</td>
                  <td>60</td>
                  <td>68.06</td>
                  <td>166.44</td>
                  <td>52.33</td>
                  <td>1.95</td>
                </tr>
                <tr>
                  <td>471</td>
                  <td>jiangyou</td>
                  <td>92</td>
                  <td>CN</td>
                  <td>1528905561</td>
                  <td>64</td>
                  <td>31.78</td>
                  <td>104.73</td>
                  <td>73.30</td>
                  <td>4.18</td>
                </tr>
                <tr>
                  <td>472</td>
                  <td>ambilobe</td>
                  <td>8</td>
                  <td>MG</td>
                  <td>1528905561</td>
                  <td>44</td>
                  <td>-13.19</td>
                  <td>49.05</td>
                  <td>80.95</td>
                  <td>13.80</td>
                </tr>
                <tr>
                  <td>473</td>
                  <td>shebunino</td>
                  <td>0</td>
                  <td>RU</td>
                  <td>1528905561</td>
                  <td>69</td>
                  <td>57.66</td>
                  <td>40.04</td>
                  <td>59.98</td>
                  <td>14.14</td>
                </tr>
                <tr>
                  <td>474</td>
                  <td>broome</td>
                  <td>20</td>
                  <td>GB</td>
                  <td>1528903200</td>
                  <td>52</td>
                  <td>52.47</td>
                  <td>1.45</td>
                  <td>71.60</td>
                  <td>11.41</td>
                </tr>
                <tr>
                  <td>475</td>
                  <td>biedenkopf</td>
                  <td>75</td>
                  <td>DE</td>
                  <td>1528903200</td>
                  <td>71</td>
                  <td>50.92</td>
                  <td>8.53</td>
                  <td>59.00</td>
                  <td>6.93</td>
                </tr>
                <tr>
                  <td>476</td>
                  <td>aquiraz</td>
                  <td>20</td>
                  <td>BR</td>
                  <td>1528905600</td>
                  <td>52</td>
                  <td>-3.90</td>
                  <td>-38.39</td>
                  <td>87.80</td>
                  <td>19.46</td>
                </tr>
                <tr>
                  <td>477</td>
                  <td>karangasem</td>
                  <td>20</td>
                  <td>ID</td>
                  <td>1528905563</td>
                  <td>100</td>
                  <td>-6.70</td>
                  <td>108.49</td>
                  <td>81.40</td>
                  <td>15.70</td>
                </tr>
                <tr>
                  <td>478</td>
                  <td>boca do acre</td>
                  <td>76</td>
                  <td>BR</td>
                  <td>1528905563</td>
                  <td>77</td>
                  <td>-8.76</td>
                  <td>-67.39</td>
                  <td>83.56</td>
                  <td>2.84</td>
                </tr>
                <tr>
                  <td>479</td>
                  <td>la antigua</td>
                  <td>48</td>
                  <td>CO</td>
                  <td>1528905564</td>
                  <td>94</td>
                  <td>6.72</td>
                  <td>-76.08</td>
                  <td>68.35</td>
                  <td>1.50</td>
                </tr>
                <tr>
                  <td>480</td>
                  <td>sibolga</td>
                  <td>76</td>
                  <td>ID</td>
                  <td>1528905564</td>
                  <td>94</td>
                  <td>1.74</td>
                  <td>98.78</td>
                  <td>74.56</td>
                  <td>1.95</td>
                </tr>
                <tr>
                  <td>481</td>
                  <td>glebychevo</td>
                  <td>68</td>
                  <td>RU</td>
                  <td>1528905564</td>
                  <td>46</td>
                  <td>60.44</td>
                  <td>28.72</td>
                  <td>60.79</td>
                  <td>4.63</td>
                </tr>
                <tr>
                  <td>482</td>
                  <td>campos altos</td>
                  <td>0</td>
                  <td>BR</td>
                  <td>1528905564</td>
                  <td>62</td>
                  <td>-19.70</td>
                  <td>-46.17</td>
                  <td>79.69</td>
                  <td>6.42</td>
                </tr>
                <tr>
                  <td>483</td>
                  <td>santiago del estero</td>
                  <td>0</td>
                  <td>AR</td>
                  <td>1528905565</td>
                  <td>49</td>
                  <td>-27.80</td>
                  <td>-64.26</td>
                  <td>52.33</td>
                  <td>6.20</td>
                </tr>
                <tr>
                  <td>484</td>
                  <td>banff</td>
                  <td>24</td>
                  <td>CA</td>
                  <td>1528905565</td>
                  <td>36</td>
                  <td>51.18</td>
                  <td>-115.57</td>
                  <td>48.01</td>
                  <td>2.17</td>
                </tr>
                <tr>
                  <td>485</td>
                  <td>santa helena</td>
                  <td>36</td>
                  <td>BR</td>
                  <td>1528905565</td>
                  <td>71</td>
                  <td>-2.23</td>
                  <td>-45.30</td>
                  <td>88.51</td>
                  <td>6.53</td>
                </tr>
                <tr>
                  <td>486</td>
                  <td>lewiston</td>
                  <td>1</td>
                  <td>US</td>
                  <td>1528901760</td>
                  <td>55</td>
                  <td>46.42</td>
                  <td>-117.02</td>
                  <td>64.40</td>
                  <td>4.70</td>
                </tr>
                <tr>
                  <td>487</td>
                  <td>bouna</td>
                  <td>0</td>
                  <td>CI</td>
                  <td>1528905567</td>
                  <td>78</td>
                  <td>9.27</td>
                  <td>-3.00</td>
                  <td>89.86</td>
                  <td>4.18</td>
                </tr>
                <tr>
                  <td>488</td>
                  <td>upington</td>
                  <td>0</td>
                  <td>ZA</td>
                  <td>1528902000</td>
                  <td>19</td>
                  <td>-28.46</td>
                  <td>21.24</td>
                  <td>69.80</td>
                  <td>5.82</td>
                </tr>
                <tr>
                  <td>489</td>
                  <td>acaponeta</td>
                  <td>68</td>
                  <td>MX</td>
                  <td>1528905567</td>
                  <td>100</td>
                  <td>22.49</td>
                  <td>-105.36</td>
                  <td>77.35</td>
                  <td>4.29</td>
                </tr>
                <tr>
                  <td>490</td>
                  <td>orito</td>
                  <td>88</td>
                  <td>CO</td>
                  <td>1528905567</td>
                  <td>97</td>
                  <td>0.67</td>
                  <td>-76.88</td>
                  <td>70.42</td>
                  <td>2.73</td>
                </tr>
                <tr>
                  <td>491</td>
                  <td>vao</td>
                  <td>0</td>
                  <td>EE</td>
                  <td>1528905567</td>
                  <td>45</td>
                  <td>59.10</td>
                  <td>26.19</td>
                  <td>62.95</td>
                  <td>5.41</td>
                </tr>
                <tr>
                  <td>492</td>
                  <td>nkhotakota</td>
                  <td>0</td>
                  <td>MW</td>
                  <td>1528905568</td>
                  <td>74</td>
                  <td>-12.93</td>
                  <td>34.30</td>
                  <td>70.69</td>
                  <td>6.08</td>
                </tr>
                <tr>
                  <td>493</td>
                  <td>boyuibe</td>
                  <td>90</td>
                  <td>BO</td>
                  <td>1528902000</td>
                  <td>47</td>
                  <td>-20.43</td>
                  <td>-63.28</td>
                  <td>55.40</td>
                  <td>5.82</td>
                </tr>
                <tr>
                  <td>494</td>
                  <td>necochea</td>
                  <td>80</td>
                  <td>AR</td>
                  <td>1528905573</td>
                  <td>81</td>
                  <td>-38.55</td>
                  <td>-58.74</td>
                  <td>50.26</td>
                  <td>14.03</td>
                </tr>
                <tr>
                  <td>495</td>
                  <td>paitan</td>
                  <td>0</td>
                  <td>CN</td>
                  <td>1528902000</td>
                  <td>78</td>
                  <td>23.49</td>
                  <td>113.78</td>
                  <td>77.00</td>
                  <td>11.18</td>
                </tr>
                <tr>
                  <td>496</td>
                  <td>claresholm</td>
                  <td>1</td>
                  <td>CA</td>
                  <td>1528902000</td>
                  <td>31</td>
                  <td>50.02</td>
                  <td>-113.58</td>
                  <td>60.80</td>
                  <td>23.04</td>
                </tr>
                <tr>
                  <td>497</td>
                  <td>sabha</td>
                  <td>24</td>
                  <td>LY</td>
                  <td>1528905575</td>
                  <td>10</td>
                  <td>27.03</td>
                  <td>14.43</td>
                  <td>112.45</td>
                  <td>9.66</td>
                </tr>
                <tr>
                  <td>498</td>
                  <td>northam</td>
                  <td>40</td>
                  <td>GB</td>
                  <td>1528903200</td>
                  <td>77</td>
                  <td>51.04</td>
                  <td>-4.21</td>
                  <td>66.20</td>
                  <td>12.75</td>
                </tr>
                <tr>
                  <td>499</td>
                  <td>sarakhs</td>
                  <td>80</td>
                  <td>TM</td>
                  <td>1528902000</td>
                  <td>37</td>
                  <td>36.54</td>
                  <td>61.16</td>
                  <td>82.40</td>
                  <td>6.93</td>
                </tr>
                <tr>
                  <td>500</td>
                  <td>moroni</td>
                  <td>0</td>
                  <td>US</td>
                  <td>1528905577</td>
                  <td>19</td>
                  <td>39.52</td>
                  <td>-111.59</td>
                  <td>70.69</td>
                  <td>3.06</td>
                </tr>
                <tr>
                  <td>501</td>
                  <td>nisia floresta</td>
                  <td>75</td>
                  <td>BR</td>
                  <td>1528905600</td>
                  <td>51</td>
                  <td>-6.09</td>
                  <td>-35.21</td>
                  <td>86.00</td>
                  <td>24.16</td>
                </tr>
                <tr>
                  <td>502</td>
                  <td>yantarnyy</td>
                  <td>20</td>
                  <td>RU</td>
                  <td>1528903800</td>
                  <td>72</td>
                  <td>54.87</td>
                  <td>19.94</td>
                  <td>64.40</td>
                  <td>6.71</td>
                </tr>
                <tr>
                  <td>503</td>
                  <td>banjar</td>
                  <td>12</td>
                  <td>ID</td>
                  <td>1528905582</td>
                  <td>88</td>
                  <td>-7.37</td>
                  <td>108.54</td>
                  <td>71.50</td>
                  <td>3.62</td>
                </tr>
                <tr>
                  <td>504</td>
                  <td>khandyga</td>
                  <td>48</td>
                  <td>RU</td>
                  <td>1528905583</td>
                  <td>47</td>
                  <td>62.65</td>
                  <td>135.58</td>
                  <td>54.85</td>
                  <td>6.20</td>
                </tr>
                <tr>
                  <td>505</td>
                  <td>heinola</td>
                  <td>0</td>
                  <td>FI</td>
                  <td>1528903200</td>
                  <td>33</td>
                  <td>61.20</td>
                  <td>26.03</td>
                  <td>62.60</td>
                  <td>3.36</td>
                </tr>
                <tr>
                  <td>506</td>
                  <td>sept-iles</td>
                  <td>40</td>
                  <td>CA</td>
                  <td>1528902000</td>
                  <td>47</td>
                  <td>50.20</td>
                  <td>-66.38</td>
                  <td>55.40</td>
                  <td>16.11</td>
                </tr>
                <tr>
                  <td>507</td>
                  <td>yenagoa</td>
                  <td>92</td>
                  <td>NG</td>
                  <td>1528905584</td>
                  <td>80</td>
                  <td>4.92</td>
                  <td>6.26</td>
                  <td>81.94</td>
                  <td>11.01</td>
                </tr>
                <tr>
                  <td>508</td>
                  <td>pontianak</td>
                  <td>44</td>
                  <td>ID</td>
                  <td>1528905585</td>
                  <td>99</td>
                  <td>-0.02</td>
                  <td>109.34</td>
                  <td>77.89</td>
                  <td>3.40</td>
                </tr>
                <tr>
                  <td>509</td>
                  <td>okha</td>
                  <td>80</td>
                  <td>RU</td>
                  <td>1528905585</td>
                  <td>90</td>
                  <td>53.59</td>
                  <td>142.95</td>
                  <td>40.09</td>
                  <td>10.78</td>
                </tr>
                <tr>
                  <td>510</td>
                  <td>bismarck</td>
                  <td>1</td>
                  <td>US</td>
                  <td>1528905300</td>
                  <td>30</td>
                  <td>46.81</td>
                  <td>-100.78</td>
                  <td>71.60</td>
                  <td>12.75</td>
                </tr>
                <tr>
                  <td>511</td>
                  <td>dunedin</td>
                  <td>92</td>
                  <td>NZ</td>
                  <td>1528905434</td>
                  <td>100</td>
                  <td>-45.87</td>
                  <td>170.50</td>
                  <td>43.33</td>
                  <td>2.95</td>
                </tr>
                <tr>
                  <td>512</td>
                  <td>dabakala</td>
                  <td>24</td>
                  <td>CI</td>
                  <td>1528905587</td>
                  <td>74</td>
                  <td>8.36</td>
                  <td>-4.43</td>
                  <td>88.78</td>
                  <td>4.52</td>
                </tr>
                <tr>
                  <td>513</td>
                  <td>pitelino</td>
                  <td>64</td>
                  <td>RU</td>
                  <td>1528905589</td>
                  <td>66</td>
                  <td>54.58</td>
                  <td>41.81</td>
                  <td>69.70</td>
                  <td>11.23</td>
                </tr>
                <tr>
                  <td>514</td>
                  <td>egvekinot</td>
                  <td>0</td>
                  <td>RU</td>
                  <td>1528905592</td>
                  <td>71</td>
                  <td>66.32</td>
                  <td>-179.17</td>
                  <td>37.30</td>
                  <td>2.51</td>
                </tr>
                <tr>
                  <td>515</td>
                  <td>melo</td>
                  <td>56</td>
                  <td>UY</td>
                  <td>1528905592</td>
                  <td>78</td>
                  <td>-32.37</td>
                  <td>-54.17</td>
                  <td>50.08</td>
                  <td>22.08</td>
                </tr>
                <tr>
                  <td>516</td>
                  <td>mbeya</td>
                  <td>0</td>
                  <td>TZ</td>
                  <td>1528905593</td>
                  <td>40</td>
                  <td>-8.91</td>
                  <td>33.47</td>
                  <td>71.05</td>
                  <td>3.85</td>
                </tr>
                <tr>
                  <td>517</td>
                  <td>kochi</td>
                  <td>90</td>
                  <td>IN</td>
                  <td>1528903800</td>
                  <td>94</td>
                  <td>9.96</td>
                  <td>76.25</td>
                  <td>77.00</td>
                  <td>2.24</td>
                </tr>
                <tr>
                  <td>518</td>
                  <td>notse</td>
                  <td>56</td>
                  <td>TG</td>
                  <td>1528905594</td>
                  <td>76</td>
                  <td>6.95</td>
                  <td>1.17</td>
                  <td>86.62</td>
                  <td>8.77</td>
                </tr>
                <tr>
                  <td>519</td>
                  <td>amuntai</td>
                  <td>36</td>
                  <td>ID</td>
                  <td>1528905596</td>
                  <td>88</td>
                  <td>-2.42</td>
                  <td>115.25</td>
                  <td>77.17</td>
                  <td>2.17</td>
                </tr>
                <tr>
                  <td>520</td>
                  <td>san juan</td>
                  <td>90</td>
                  <td>PH</td>
                  <td>1528902000</td>
                  <td>100</td>
                  <td>14.60</td>
                  <td>121.03</td>
                  <td>77.00</td>
                  <td>10.29</td>
                </tr>
                <tr>
                  <td>521</td>
                  <td>rocha</td>
                  <td>56</td>
                  <td>UY</td>
                  <td>1528905597</td>
                  <td>93</td>
                  <td>-34.48</td>
                  <td>-54.34</td>
                  <td>49.99</td>
                  <td>21.18</td>
                </tr>
                <tr>
                  <td>522</td>
                  <td>elizabeth city</td>
                  <td>90</td>
                  <td>US</td>
                  <td>1528904640</td>
                  <td>83</td>
                  <td>36.30</td>
                  <td>-76.22</td>
                  <td>78.80</td>
                  <td>12.75</td>
                </tr>
                <tr>
                  <td>523</td>
                  <td>narathiwat</td>
                  <td>75</td>
                  <td>TH</td>
                  <td>1528902000</td>
                  <td>83</td>
                  <td>6.43</td>
                  <td>101.80</td>
                  <td>82.40</td>
                  <td>4.70</td>
                </tr>
                <tr>
                  <td>524</td>
                  <td>acari</td>
                  <td>0</td>
                  <td>BR</td>
                  <td>1528905599</td>
                  <td>48</td>
                  <td>-6.44</td>
                  <td>-36.64</td>
                  <td>84.10</td>
                  <td>15.26</td>
                </tr>
                <tr>
                  <td>525</td>
                  <td>puerto carreno</td>
                  <td>40</td>
                  <td>CO</td>
                  <td>1528902000</td>
                  <td>74</td>
                  <td>6.19</td>
                  <td>-67.49</td>
                  <td>84.20</td>
                  <td>3.36</td>
                </tr>
                <tr>
                  <td>526</td>
                  <td>troitskiy</td>
                  <td>0</td>
                  <td>RU</td>
                  <td>1528903800</td>
                  <td>48</td>
                  <td>45.15</td>
                  <td>38.14</td>
                  <td>82.40</td>
                  <td>6.71</td>
                </tr>
                <tr>
                  <td>527</td>
                  <td>dhidhdhoo</td>
                  <td>88</td>
                  <td>MV</td>
                  <td>1528905605</td>
                  <td>100</td>
                  <td>6.88</td>
                  <td>73.10</td>
                  <td>82.39</td>
                  <td>12.24</td>
                </tr>
                <tr>
                  <td>528</td>
                  <td>santa fe</td>
                  <td>12</td>
                  <td>AR</td>
                  <td>1528905642</td>
                  <td>84</td>
                  <td>-31.62</td>
                  <td>-60.70</td>
                  <td>47.47</td>
                  <td>10.45</td>
                </tr>
                <tr>
                  <td>529</td>
                  <td>kuytun</td>
                  <td>20</td>
                  <td>RU</td>
                  <td>1528905610</td>
                  <td>73</td>
                  <td>54.34</td>
                  <td>101.51</td>
                  <td>64.30</td>
                  <td>2.62</td>
                </tr>
                <tr>
                  <td>530</td>
                  <td>evans</td>
                  <td>1</td>
                  <td>US</td>
                  <td>1528904100</td>
                  <td>41</td>
                  <td>40.38</td>
                  <td>-104.69</td>
                  <td>78.80</td>
                  <td>3.36</td>
                </tr>
                <tr>
                  <td>531</td>
                  <td>sokoni</td>
                  <td>0</td>
                  <td>CD</td>
                  <td>1528905646</td>
                  <td>37</td>
                  <td>-12.89</td>
                  <td>28.78</td>
                  <td>74.56</td>
                  <td>4.07</td>
                </tr>
                <tr>
                  <td>532</td>
                  <td>sovetskiy</td>
                  <td>76</td>
                  <td>RU</td>
                  <td>1528905619</td>
                  <td>85</td>
                  <td>56.76</td>
                  <td>48.47</td>
                  <td>61.33</td>
                  <td>14.03</td>
                </tr>
                <tr>
                  <td>533</td>
                  <td>pagudpud</td>
                  <td>90</td>
                  <td>PH</td>
                  <td>1528902000</td>
                  <td>100</td>
                  <td>18.56</td>
                  <td>120.79</td>
                  <td>77.00</td>
                  <td>13.87</td>
                </tr>
                <tr>
                  <td>534</td>
                  <td>southbridge</td>
                  <td>90</td>
                  <td>US</td>
                  <td>1528903440</td>
                  <td>82</td>
                  <td>42.08</td>
                  <td>-72.03</td>
                  <td>69.80</td>
                  <td>19.46</td>
                </tr>
                <tr>
                  <td>535</td>
                  <td>brazzaville</td>
                  <td>8</td>
                  <td>CD</td>
                  <td>1528902000</td>
                  <td>55</td>
                  <td>-4.27</td>
                  <td>15.27</td>
                  <td>86.00</td>
                  <td>5.82</td>
                </tr>
                <tr>
                  <td>536</td>
                  <td>tutoia</td>
                  <td>40</td>
                  <td>BR</td>
                  <td>1528902000</td>
                  <td>52</td>
                  <td>-2.76</td>
                  <td>-42.27</td>
                  <td>91.40</td>
                  <td>8.05</td>
                </tr>
                <tr>
                  <td>537</td>
                  <td>harlingen</td>
                  <td>75</td>
                  <td>US</td>
                  <td>1528902900</td>
                  <td>62</td>
                  <td>26.19</td>
                  <td>-97.70</td>
                  <td>89.60</td>
                  <td>10.29</td>
                </tr>
                <tr>
                  <td>538</td>
                  <td>calamar</td>
                  <td>92</td>
                  <td>CO</td>
                  <td>1528905629</td>
                  <td>100</td>
                  <td>1.96</td>
                  <td>-72.65</td>
                  <td>70.87</td>
                  <td>2.95</td>
                </tr>
                <tr>
                  <td>539</td>
                  <td>road town</td>
                  <td>40</td>
                  <td>VG</td>
                  <td>1528905600</td>
                  <td>66</td>
                  <td>18.42</td>
                  <td>-64.62</td>
                  <td>87.80</td>
                  <td>12.75</td>
                </tr>
                <tr>
                  <td>540</td>
                  <td>tabas</td>
                  <td>36</td>
                  <td>IR</td>
                  <td>1528905630</td>
                  <td>11</td>
                  <td>33.60</td>
                  <td>56.92</td>
                  <td>94.27</td>
                  <td>6.98</td>
                </tr>
                <tr>
                  <td>541</td>
                  <td>shieli</td>
                  <td>88</td>
                  <td>KZ</td>
                  <td>1528905630</td>
                  <td>41</td>
                  <td>44.18</td>
                  <td>66.74</td>
                  <td>67.27</td>
                  <td>14.81</td>
                </tr>
                <tr>
                  <td>542</td>
                  <td>scalea</td>
                  <td>36</td>
                  <td>IT</td>
                  <td>1528905631</td>
                  <td>100</td>
                  <td>39.82</td>
                  <td>15.79</td>
                  <td>70.06</td>
                  <td>5.30</td>
                </tr>
                <tr>
                  <td>543</td>
                  <td>san andres</td>
                  <td>68</td>
                  <td>PH</td>
                  <td>1528905632</td>
                  <td>100</td>
                  <td>13.32</td>
                  <td>122.68</td>
                  <td>83.47</td>
                  <td>22.64</td>
                </tr>
                <tr>
                  <td>544</td>
                  <td>muisne</td>
                  <td>92</td>
                  <td>EC</td>
                  <td>1528905633</td>
                  <td>84</td>
                  <td>0.61</td>
                  <td>-80.02</td>
                  <td>76.90</td>
                  <td>4.63</td>
                </tr>
                <tr>
                  <td>545</td>
                  <td>ati</td>
                  <td>20</td>
                  <td>TD</td>
                  <td>1528905633</td>
                  <td>25</td>
                  <td>13.21</td>
                  <td>18.34</td>
                  <td>104.53</td>
                  <td>4.97</td>
                </tr>
                <tr>
                  <td>546</td>
                  <td>san luis</td>
                  <td>0</td>
                  <td>AR</td>
                  <td>1528905472</td>
                  <td>53</td>
                  <td>-33.30</td>
                  <td>-66.34</td>
                  <td>42.43</td>
                  <td>2.62</td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
      </article>
    </div>
    <!-- End of container -->

    <!-- Start of footer -->
    <footer class="footer navbar-fixed-bottom">
      <div class="two-toned-footer-color"></div>
      <p class="text-muted text-muted-footer text-center">
        &copy; Copyright Coding Bootcamp 2017
      </p>
    </footer>
    <!-- End of footer -->

    <!-- jQuery CDN -->
    <script type="text/javascript" src="https://code.jquery.com/jquery-2.1.4.min.js"></script>

    <!-- Bootstrap CDN -->
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/js/bootstrap.min.js"></script>
  </body>

</html>

```