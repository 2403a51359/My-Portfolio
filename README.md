<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet"/>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Inter', sans-serif;
      line-height: 1.6;
      background: linear-gradient(135deg, #0a0a0a 0%, #1a0a1a 50%, #0a0a1a 100%);
      color: #e0e0e0;
      min-height: 100vh;
    }

    header {
      background: linear-gradient(135deg, #8b0000 0%, #4b0082 100%);
      color: #fff;
      padding: 60px 20px;
      text-align: center;
      position: relative;
      overflow: hidden;
      animation: fadeIn 1.5s ease-in-out;
    }

    header::before {
      content: '';
      position: absolute;
      top: -50%;
      left: -50%;
      width: 200%;
      height: 200%;
      background: radial-gradient(circle, rgba(255, 0, 100, 0.1) 0%, transparent 70%);
      animation: pulse 8s infinite linear;
    }

    header h1 {
      font-size: 2.5rem;
      margin-bottom: 10px;
      position: relative;
      z-index: 1;
      animation: slideDown 1s ease-out;
    }

    header p {
      font-size: 1.2rem;
      color: #f0f0f0;
      position: relative;
      z-index: 1;
      animation: slideUp 1s ease-out;
    }

    section {
      padding: 60px 20px;
      max-width: 1200px;
      margin: auto;
      animation: fadeIn 1.5s ease-in-out;
    }

    h2 {
      font-size: 2rem;
      margin-bottom: 30px;
      background: linear-gradient(90deg, #ff4d4d 0%, #9932cc 100%);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      border-left: 4px solid #9932cc;
      padding-left: 10px;
      position: relative;
      animation: slideInLeft 1s ease-out;
    }

    .about p {
      max-width: 700px;
      font-size: 1rem;
      color: #d0d0d0;
      animation: fadeIn 1.5s ease-in-out;
    }

    .contact form {
      display: flex;
      flex-direction: column;
      gap: 15px;
      max-width: 500px;
      animation: fadeIn 1.5s ease-in-out;
    }

    .contact input,
    .contact textarea {
      padding: 10px;
      border: 1px solid rgba(153, 50, 204, 0.3);
      border-radius: 4px;
      font-size: 1rem;
      background-color: #1e1e1e;
      color: #e0e0e0;
      transition: 0.3s ease;
    }

    .contact input:focus,
    .contact textarea:focus {
      outline: none;
      border-color: #9932cc;
      box-shadow: 0 0 10px rgba(153, 50, 204, 0.3);
    }

    .contact button {
      padding: 12px;
      background: linear-gradient(90deg, #ff4d4d 0%, #9932cc 100%);
      color: #fff;
      border: none;
      font-weight: bold;
      border-radius: 4px;
      cursor: pointer;
      transition: 0.3s ease;
      position: relative;
      overflow: hidden;
    }

    .contact button::before {
      content: '';
      position: absolute;
      top: 50%;
      left: 50%;
      width: 0;
      height: 0;
      background: rgba(255, 255, 255, 0.2);
      border-radius: 50%;
      transform: translate(-50%, -50%);
      transition: width 0.6s, height 0.6s;
    }

    .contact button:hover::before {
      width: 300px;
      height: 300px;
    }

    .contact button:hover {
      transform: translateY(-2px);
      box-shadow: 0 5px 15px rgba(153, 50, 204, 0.4);
    }

    .social-links {
      margin-top: 30px;
      display: flex;
      gap: 20px;
      animation: fadeIn 1.5s ease-in-out;
    }

    .social-links a {
      display: flex;
      align-items: center;
      gap: 10px;
      color: #d0d0d0;
      text-decoration: none;
      padding: 10px 15px;
      border-radius: 30px;
      background: linear-gradient(145deg, #1e1e1e 0%, #2a2a2a 100%);
      border: 1px solid rgba(153, 50, 204, 0.3);
      transition: 0.3s ease;
    }

    .social-links a:hover {
      background: linear-gradient(90deg, rgba(255, 77, 77, 0.2), rgba(153, 50, 204, 0.2));
      transform: translateY(-3px);
      box-shadow: 0 5px 15px rgba(153, 50, 204, 0.3);
    }

    .social-links i {
      font-size: 1.2rem;
      background: linear-gradient(90deg, #ff4d4d 0%, #9932cc 100%);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }

    .education {
      padding: 60px 20px;
      background: linear-gradient(145deg, #1a1a1a 0%, #222222 100%);
    }

    .education h2 {
      text-align: center;
      margin-bottom: 40px;
      background: linear-gradient(90deg, #ff4d4d 0%, #9932cc 100%);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      font-size: 2rem;
      border: none;
      padding-left: 0;
      animation: fadeIn 1.5s ease-in-out;
    }

    .education-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 30px;
    }

    .education-card {
      background: linear-gradient(145deg, #1e1e1e 0%, #2a2a2a 100%);
      border-radius: 12px;
      padding: 25px;
      box-shadow: 0 4px 15px rgba(0, 0, 0, 0.3);
      border: 1px solid rgba(153, 50, 204, 0.2);
      transition: 0.3s ease;
      position: relative;
      overflow: hidden;
      animation: fadeInUp 1s ease-out;
    }

    .education-card::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 5px;
      height: 100%;
      background: linear-gradient(to bottom, #ff4d4d, #9932cc);
    }

    .education-card:hover {
      transform: translateY(-5px);
      box-shadow: 0 8px 25px rgba(153, 50, 204, 0.3);
      border-color: #9932cc;
    }

    .education-card h3 {
      font-size: 1.5rem;
      margin-bottom: 15px;
      background: linear-gradient(90deg, #ff4d4d 0%, #9932cc 100%);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }

    .education-card .institution {
      font-size: 1.1rem;
      font-weight: 600;
      color: #d0d0d0;
      margin-bottom: 5px;
    }

    .education-card .year {
      font-size: 0.95rem;
      color: #a0a0a0;
      margin-bottom: 10px;
    }

    .education-card .score {
      font-size: 1rem;
      color: #b0b0b0;
      font-style: italic;
    }

    .education-card .icon {
      position: absolute;
      top: 20px;
      right: 20px;
      font-size: 2rem;
      background: linear-gradient(90deg, #ff4d4d 0%, #9932cc 100%);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      opacity: 0.3;
    }

    .courses {
      padding: 60px 20px;
    }

    .courses h2 {
      text-align: center;
      margin-bottom: 40px;
      background: linear-gradient(90deg, #ff4d4d 0%, #9932cc 100%);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      font-size: 2rem;
      border: none;
      padding-left: 0;
      animation: fadeIn 1.5s ease-in-out;
    }

    .course-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 20px;
    }

    .course-card {
      background: linear-gradient(145deg, #1e1e1e 0%, #2a2a2a 100%);
      border-radius: 8px;
      overflow: hidden;
      text-align: center;
      box-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
      transition: 0.3s ease;
      border: 1px solid rgba(153, 50, 204, 0.2);
      animation: fadeInUp 1s ease-out;
      position: relative;
    }

    .course-card::after {
      content: '';
      position: absolute;
      bottom: 0;
      left: 0;
      width: 100%;
      height: 3px;
      background: linear-gradient(90deg, #ff4d4d 0%, #9932cc 100%);
      transform: scaleX(0);
      transform-origin: left;
      transition: transform 0.3s ease;
    }

    .course-card:hover::after {
      transform: scaleX(1);
    }

    .course-card:hover {
      transform: translateY(-5px);
      box-shadow: 0 8px 20px rgba(153, 50, 204, 0.3);
      border-color: #9932cc;
    }

    .course-card img {
      width: 100%;
      height: auto;
      display: block;
      transition: transform 0.5s ease;
    }

    .course-card:hover img {
      transform: scale(1.05);
    }

    .course-card p {
      padding: 15px;
      font-size: 0.95rem;
      color: #d0d0d0;
    }

    footer {
      text-align: center;
      padding: 20px;
      background: linear-gradient(135deg, #8b0000 0%, #4b0082 100%);
      color: #ccc;
      font-size: 0.9rem;
      animation: fadeIn 1.5s ease-in-out;
    }

    @media (max-width: 600px) {
      header h1 {
        font-size: 2rem;
      }
      section {
        padding: 40px 15px;
      }
      .social-links {
        flex-direction: column;
        align-items: center;
      }
      .education-grid {
        grid-template-columns: 1fr;
      }
    }

    /* Animations */
    @keyframes fadeIn {
      from {
        opacity: 0;
      }
      to {
        opacity: 1;
      }
    }

    @keyframes slideDown {
      from {
        transform: translateY(-30px);
        opacity: 0;
      }
      to {
        transform: translateY(0);
        opacity: 1;
      }
    }

    @keyframes slideUp {
      from {
        transform: translateY(30px);
        opacity: 0;
      }
      to {
        transform: translateY(0);
        opacity: 1;
      }
    }

    @keyframes slideInLeft {
      from {
        transform: translateX(-30px);
        opacity: 0;
      }
      to {
        transform: translateX(0);
        opacity: 1;
      }
    }

    @keyframes fadeInUp {
      from {
        transform: translateY(30px);
        opacity: 0;
      }
      to {
        transform: translateY(0);
        opacity: 1;
      }
    }

    @keyframes pulse {
      0% {
        transform: rotate(0deg);
      }
      100% {
        transform: rotate(360deg);
      }
    }
  </style>
</head>
<body>

  <header>
    <h1>Gadamalla Manikanta</h1>
    <p>My Portfolio</p>
  </header>

  <section class="about">
    <h2>About Me</h2>
    <p>
      I am a passionate developer with experience in building responsive websites and applications.
      I enjoy exploring new technologies, solving real-world problems, and constantly learning.
    </p>
  </section>

  <section class="education">
    <h2>Education</h2>
    <div class="education-grid">
      <div class="education-card">
        <i class="fas fa-graduation-cap icon"></i>
        <h3>B.Tech in Computer Science</h3>
        <p class="institution">SR University</p>
        <p class="year">2024-2028</p>
        
      </div>
      <div class="education-card">
        <i class="fas fa-school icon"></i>
        <h3>Intermediate (MPC)</h3>
        <p class="institution">Alphores Junior College</p>
        <p class="year">2022 - 2024</p>
        <p class="score">Percentage: 95%</p>
      </div>
      <div class="education-card">
        <i class="fas fa-book icon"></i>
        <h3>SSC (10th Grade)</h3>
        <p class="institution">Tetra Hedron Model School</p>
        <p class="year">2017 - 2018</p>
        <p class="score">CGPA: 9.8</p>
      </div>
    </div>
  </section>

  <section class="courses">
    <h2>My Courses</h2>
    <div class="course-grid">
      <div class="course-card">
        <img src="https://d3lkc3n5th01x7.cloudfront.net/wp-content/uploads/2023/12/04031617/AI-assisted-coding.png" alt="AI Assisted Coding" />
        <p>PC - AI Assisted Coding</p>
      </div>
      <div class="course-card">
        <img src="https://www.inventateq.com/inventateq-assets/cloud-computing-project.webp" alt="Cloud Computing" />
        <p>PC - Cloud Computing</p>
      </div>
      <div class="course-card">
        <img src="https://datacity.in/wp-content/uploads/2024/11/data-anallysis.webp" alt="Data Analytics and Visualization" />
        <p>PC - Data Analytics and Visualization</p>
      </div>
      <div class="course-card">
        <img src="https://assets.htmlgoodies.com/uploads/2021/08/HTML5-420x420.png" alt="Web Tech & Mobile Programming" />
        <p>PC - Web Technologies and Mobile Programming</p>
      </div>
      <div class="course-card">
        <img src="https://blog.greencloudvps.com/wp-content/uploads/2024/03/database-management-system-3-768x432.jpg" alt="Information Management System" />
        <p>PC - Information Management System</p>
      </div>
      <div class="course-card">
        <img src="https://pakcollege.edu.pk/wp-content/uploads/2023/11/WhatsApp-Image-2023-11-11-at-1.20.18-PM.jpeg" alt="Computer Networks" />
        <p>PC - Computer Networks</p>
      </div>

      <div class="course-card">
        <img src="http://citypng.com/public/uploads/preview/hd-python-logo-symbol-transparent-png-735811696257415dbkifcuokn.png" alt="Python" />
        <p>PEPSP2 - Problem Solving Using Python</p>
      </div>
      <div class="course-card">
        <img src="https://images.shiksha.com/mediadata/images/articles/1709294752phpf4ythX.jpeg" alt="Operating Systems" />
        <p>PC - Operating Systems</p>
      </div>
      <div class="course-card">
        <img src="https://play-lh.googleusercontent.com/1H4LOr4r-mniNNPvSfF9eb0uV99aPxCaXWESJYvBp2332UauRNCHlLwWOWGw98YCUfY=w480-h960-rw" alt="Computer Architecture" />
        <p>PC - Computer Organization and Architecture</p>
      </div>
      <div class="course-card">
        <img src="https://miro.medium.com/v2/resize:fit:1100/format:webp/1*rd3cktHQpQlJyhxEas3hMQ.png" alt="Discrete Mathematics" />
        <p>PC - Discrete Mathematical Structures</p>
      </div>

      <div class="course-card">
        <img src="https://www.clipartmax.com/png/middle/351-3515666_c-language-global-or-external-variables-with-examples-c-programming-logo.png" alt="C Language" />
        <p>PEPSP1 - Problem Solving Using C</p>
      </div>
      <div class="course-card">
        <img src="https://www.japan-academy.in/blog/wp-content/uploads/2021/04/Difference-between-Hiragana-and-Katakana-in-Japanese-Language-870x600.jpg" alt="Japanese Language" />
        <p>PELNG1 - Japanese</p>
      </div>
    </div>
  </section>

  <section class="contact">
    <h2>Contact Me</h2>
    <form>
      <input type="text" placeholder="Your Name" required />
      <input type="email" placeholder="Your Email" required />
      <textarea rows="5" placeholder="Your Message" required></textarea>
      <button type="submit">Send Message</button>
    </form>
    
    <div class="social-links">
      <a href="www.linkedin.com/in/manikanta-gadamalla" target="_blank">
        <i class="fab fa-linkedin"></i>
        <span>LinkedIn Profile</span>
      </a>
    </div>
  </section>

  <footer>
    &copy; 2025 Your Name. All rights reserved.
  </footer>

</body>
</html>
