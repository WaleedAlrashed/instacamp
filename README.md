# InstaCamp - Instagram Clone

[![Laravel](https://img.shields.io/badge/Laravel-10.x-FF2D20?style=for-the-badge&logo=laravel&logoColor=white)](https://laravel.com)
[![MongoDB](https://img.shields.io/badge/MongoDB-4.x-47A248?style=for-the-badge&logo=mongodb&logoColor=white)](https://www.mongodb.com/)
[![PHP](https://img.shields.io/badge/PHP-8.1+-777BB4?style=for-the-badge&logo=php&logoColor=white)](https://php.net)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3.x-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)](https://tailwindcss.com)
[![Node.js](https://img.shields.io/badge/Node.js-18.x-339933?style=for-the-badge&logo=node.js&logoColor=white)](https://nodejs.org)
[![Vite](https://img.shields.io/badge/Vite-4.x-646CFF?style=for-the-badge&logo=vite&logoColor=white)](https://vitejs.dev)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)


This project is based on the tutorial from the freeCodeCamp YouTube channel: [Build an Instagram Clone with Laravel, Tailwind CSS, and More](https://www.youtube.com/watch?v=VK-2j5CNsvM)

## Prerequisites

- PHP >= 8.1
- Composer
- Node.js & npm
- MongoDB
- Git

## Installation Steps

1. **Clone the Repository**
   ```bash
   git clone <repository-url>
   cd instacamp
   ```

2. **Install PHP Dependencies**
   ```bash
   composer install
   ```

3. **Install Node Dependencies**
   ```bash
   npm install
   ```

4. **Environment Setup**
   ```bash
   # Copy the example env file
   cp .env.example .env

   # Generate application key
   php artisan key:generate
   ```

5. **Configure MongoDB**
   
   Update your `.env` file with your MongoDB connection details:
   ```env
   DB_URI="mongodb://127.0.0.1:27017/?directConnection=true&serverSelectionTimeoutMS=2000&appName=mongosh+2.4.0"
   DB_CONNECTION=mongodb
   DB_HOST=127.0.0.1
   DB_PORT=27017
   DB_DATABASE=instacamp
   DB_USERNAME=your_username     # if authentication is enabled
   DB_PASSWORD=your_password     # if authentication is enabled
   
   SESSION_DRIVER=mongodb
   SESSION_LIFETIME=120
   ```

6. **Start MongoDB**
   ```bash
   # On macOS (if installed via Homebrew)
   brew services start mongodb-community

   # On Linux
   sudo systemctl start mongod
   ```

7. **Run Database Migrations**
   ```bash
   php artisan migrate
   ```

8. **Build Assets**
   ```bash
   npm run build
   ```

9. **Start the Development Server**
   ```bash
   # In one terminal
   php artisan serve

   # In another terminal
   npm run dev
   ```

10. **Access the Application**
    - Open your browser and visit: `http://localhost:8000`

## Troubleshooting

If you encounter session-related issues:

1. Clear MongoDB sessions:
   ```bash
   mongosh
   use instacamp
   db.sessions.drop()
   ```

2. Clear Laravel cache:
   ```bash
   php artisan cache:clear
   php artisan config:clear
   php artisan view:clear
   ```

## Features

- User authentication
- Create and share posts
- Comment on posts
- Like posts
- User profiles
- Follow/Unfollow users

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).

## Acknowledgments

- [FreeCodeCamp](https://www.freecodecamp.org/) for the original tutorial
- Laravel Framework
- MongoDB