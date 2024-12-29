<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Abhishek's Data-ML Profile</title>
  <style>
    body {
      margin: 0;
      padding: 20px;
      font-family: Arial, sans-serif;
    }
    /* Container for the profile header */
    .profile-header {
      display: flex;              /* Enables horizontal (side-by-side) layout */
      align-items: center;        /* Vertically center the items in the flex container */
    }
    /* Image styles */
    .profile-header img {
      max-width: 150px;          /* Set a reasonable max width */
      border-radius: 50%;        /* Make the image circular (if it’s a square original) */
      margin-right: 20px;        /* Spacing between image and the text block */
    }
    /* Info block next to the image */
    .profile-info h1 {
      margin: 0;                 /* Remove default margin for the heading */
      font-size: 1.8em;
    }
    .profile-info p {
      margin: 5px 0;
    }
    /* Optional: Some spacing around the contact details */
    .contact-details {
      margin-top: 20px;
    }
    /* Style for the contact links */
    .contact-details a {
      color: #0077b5;            /* LinkedIn-blue color for all links */
      text-decoration: none;
      margin-right: 15px;
      font-weight: bold;
    }
    .contact-details a:hover {
      text-decoration: underline;
    }
    /* Embedded video style */
    .profile-video {
      margin-top: 40px;          /* Spacing above the video section */
    }
    .profile-video iframe {
      width: 100%;
      height: 500px;
      border: none;
    }
  </style>
</head>
<body>

  <!-- Profile Header (Image + Name + Education) -->
  <div class="profile-header">
    <img src="https://i.imgur.com/Gmhrrzf.jpeg" alt="Abhishek Jadhav">
    <div class="profile-info">
      <h1>Abhishek Jadhav</h1>
      <p><strong>Education:</strong> BS in Computer Science &amp; MS in Data Science<br>
         from the University at Buffalo</p>
      <p>3+ years of experience building ML &amp; data pipelines, ML models, performing data analysis, and designing data infrastructure.</p>
    </div>
  </div>

  <!-- Contact Details -->
  <div class="contact-details">
    <p><strong>Contact Me:</strong></p>
    <p>
      <a href="mailto:abhishekjadhavdata@gmail.com">Email</a>
      <a href="tel:+1-7162393515">Phone</a>
      <a href="https://www.linkedin.com/in/abhishekdata/" target="_blank">LinkedIn</a>
      <a href="https://github.com/abhi-dataprofile" target="_blank">GitHub</a>
    </p>
  </div>

  <!-- Introduction Video Embed -->
  <div class="profile-video">
    <h2>Introduction Video</h2>
    <iframe 
      src="https://ub.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=59f1e03e-25b8-4163-98ce-b255016a247d"
      allowfullscreen>
    </iframe>
    <p style="font-size: 0.9em; color: #555;">(Note: Camera is not visible in the video)</p>
  </div>

</body>
</html>