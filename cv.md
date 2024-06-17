<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rob Loveridge - Personal Website</title>
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">
    <link rel="stylesheet" href="style.css">
    <style>
        /* Custom Styles */
        body {
            background-color: #f8f9fa;
            color: #333;
        }

        .jumbotron {
            background-color: #ff6961;
            color: #fff;
            padding-top: 50px;
            /* Adjusted padding */
            padding-bottom: 50px;
            /* Adjusted padding */
        }

        .navbar {
            background-color: #343a40;
        }

        .navbar-dark .navbar-nav .nav-link {
            color: rgba(255, 255, 255, .8);
        }

        .navbar-dark .navbar-nav .nav-link:hover {
            color: #fff;
        }

        .social-icons a {
            font-size: 24px;
            margin-right: 15px;
            color: #333;
        }

        .profile-img, .company-img {
            float: left;
            margin-right: 20px;
            border-radius: 10px;
            /* Make the image rounded */
            border: 4px solid #fff;
            /* Add a border */
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            /* Add a shadow */
            width: 100px;
            /* Adjust the width */
            height: 100px;
            /* Adjust the height */
            object-fit: cover;
            /* Ensure the image covers the entire area */
        }
    </style>
</head>

<body>

    <!-- Navbar -->
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
        <div class="container">
            <a class="navbar-brand" href="#">Rob Loveridge</a>
            <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent"
                aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>

            <div class="collapse navbar-collapse" id="navbarSupportedContent">
                <ul class="navbar-nav ml-auto">
                    <li class="nav-item">
                        <a class="nav-link" href="index.html">Home</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="services.html">Services</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="cv.html">CV</a>
                    </li>
                </ul>
            </div>
        </div>
    </nav>

    <!-- Jumbotron -->
    <div class="jumbotron jumbotron-fluid">
        <div class="container text-center">
            <h1 class="display-4">Curriculum Vitae</h1>
        </div>
    </div>

    <!-- Main Content -->
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8">

                <!-- CV Section -->
                <section class="container cv lead">

                    <div class="experience-item">
                        <img src="img/phocas.jpg" class="company-img">
                        <h4>Customer Support Manager</h4>
                        <div class="experience-details">
                            <p><strong>Company:</strong> Phocas Software, Coventry, United Kingdom</p>
                            <p><strong>Duration:</strong> March 2022 - Present</p>
                            <p>As the Customer Support Manager I manage and coach the customer support team in UK. As a team, we deliver an awesome customer experience to our customers.</p>
                        </div>
                    </div>


                    <div class="experience-item">
                        <img src="img/gainsight.png" class="company-img">
                        <h4>Solutions Architect</h4>
                        <div class="experience-details">
                            <p><strong>Company:</strong> Gainsight, London, United Kingdom</p>
                            <p><strong>Duration:</strong> July 2021 - March 2022 (9 months)</p>
                            <p>As a Solutions Architect at Gainsight, I worked with new and existing clients to align Gainsight features & functionality to best support their CS strategy, driving towards achievement of desired outcomes.</p>
                            <p>As a Technical Account Manager, clients consulted me on best practices for Gainsight and I helped them to define architectural and data structure to support those requirements. Aside from consulting, I also acted as a Gainsight Administrator for some clients.</p>
                        </div>
                    </div>
                    
                </section>


            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer class="bg-dark text-light text-center py-3">
        <div class="container">
            <p>Robert Loveridge, Allesley Park, Coventry</p>
            <p>If you are a professional and would like to know more about me and my work, then please feel free to <a href="https://uk.linkedin.com/in/robertloveridge" target="_blank">connect on LinkedIn.</a>
            <p>Interested in seeing <a href="https://github.com/robertloveridge" target="_blank">some of my code?</a></p>
        </div>
    </footer>

    <!-- Bootstrap Icons -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.8.0/bootstrap-icons.min.js"></script>


    <!-- jQuery and Bootstrap JS -->
    <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.5.4/dist/umd/popper.min.js"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script>
</body>

</html>