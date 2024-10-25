
<script>
    let movies = [
      {
        title: "Inception",
        description: "A mind-bending thriller by Christopher Nolan.",
        rating: 4.8,
        genre: "Sci-Fi, Thriller",
        runtime: "2h 28m",
        image: "your-image-url",
        seatsAvailable: 35
      },
      {
        title: "The Dark Knight",
        description: "Batman faces the Joker in this iconic film.",
        rating: 4.9,
        genre: "Action, Crime, Drama",
        runtime: "2h 32m",
        image: "your-image-url",
        seatsAvailable: 12
      },
      {
        title: "Jigra",
        description: "A journey beyond our galaxy.",
        rating: 4.7,
        genre: "Sci-Fi, Drama",
        runtime: "2h 49m",
        image: "jigra.avif",
        seatsAvailable: 22,
        url:"https://in.bookmyshow.com/buytickets/jigra-nagpur/movie-nagp-ET00370844-MT/20241025"
      }
    ];
  </script>
  
  <style>
    body {
      font-family: Arial, sans-serif;
      color: #333;
      display: flex;
      justify-content: center;
      align-items: center;
      margin: 0;
      background: #f3f3f3;
    }
    .container {
      max-width: 900px;
      padding: 20px;
    }
    .header {
      text-align: center;
      padding: 20px 0;
      font-size: 2em;
      color: #444;
    }
    .movie {
      background: #fff;
      padding: 15px;
      margin: 10px 0;
      border-radius: 10px;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
      display: flex;
      align-items: center;
      gap: 20px;
    }
    .movie img {
      width: 120px;
      height: 160px;
      border-radius: 8px;
      object-fit: cover;
    }
    .movie-info {
      flex: 1;
    }
    .movie-title {
      font-size: 1.4em;
      margin: 0;
      color: #222;
    }
    .movie-details {
      font-size: 0.9em;
      color: #666;
      margin-top: 5px;
    }
    .rating {
      display: flex;
      align-items: center;
      margin: 8px 0;
    }
    .stars {
      color: gold;
      margin-right: 5px;
    }
    .seats {
      font-size: 0.9em;
      color: #555;
      margin-top: 5px;
    }
    .book-button {
      padding: 10px 20px;
      background: #0073e6;
      color: #fff;
      border: none;
      border-radius: 5px;
      font-size: 1em;
      cursor: pointer;
      transition: background 0.3s ease;
    }
    .book-button:hover {
      background: #005bb5;
    }
  </style>
  
  <div class="container">
    <header class="header">🎬 Book Your Movie Tickets 🎟</header>
    {#each movies as movie}
      <div class="movie">
        <img src={movie.image} alt={movie.title} />
        <div class="movie-info">
          <h2 class="movie-title">{movie.title}</h2>
          <p class="movie-details">
            {movie.genre} • {movie.runtime}
          </p>
          <div class="rating">
            <span class="stars">{"★".repeat(Math.round(movie.rating))}</span>
            <span>{movie.rating}</span>
          </div>
          <p class="seats">
            {movie.seatsAvailable > 0 ? `${movie.seatsAvailable} seats available` : "Sold Out"}
          </p>
          {#if movie.seatsAvailable > 0}
          <a href={movie.url}>
            <button class="book-button">Book Now</button>
          </a>
          {/if}
        </div>
      </div>
    {/each}
  </div>
  
  