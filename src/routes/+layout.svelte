<style>
    .navbar {
      width: 100%;
      height: 50px;
      background-color: #1d1d1d; /* Dark background for the navbar */
      color: white;
      display: flex;
      justify-content: space-evenly; /* Distribute navbar content */
      align-items: center;
    }
  
    .navbar a {
      color: white;
      text-decoration: none;
      margin: 0 1rem;
    }
  </style>
  
  <div class="navbar">
    <a href="/">Home</a>
    <a href="/login">Login</a>
    <a href="/radio">Radiologists view</a>
    <a href="/about">About</a>
    <a href="/contact">Contact</a>
    <!-- Add other links or logo as needed -->
  </div>

  <slot></slot>
  