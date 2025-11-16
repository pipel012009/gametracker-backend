# 🎮 GameTracker - Backend

Backend API para GameTracker, una aplicación de gestión de biblioteca personal de videojuegos.

## 🚀 Tecnologías

- Node.js
- Express
- MongoDB + Mongoose
- CORS

## 📦 Instalación

```bash
npm install
```

## ⚙️ Configuración

1. Copia el archivo de ejemplo:
```bash
copy .env.example .env
```

2. Edita `.env` y configura tu conexión a MongoDB:
```
PORT=5000
MONGO_URI=mongodb+srv://<usuario>:<contraseña>@cluster.mongodb.net/gametracker
```

## 🏃 Ejecutar

### Modo desarrollo
```bash
npm run dev
```

### Modo producción
```bash
npm start
```

El servidor estará disponible en `http://localhost:5000`

## 📡 Endpoints API

### Juegos
- `GET /api/games` - Obtener todos los juegos
- `GET /api/games/:id` - Obtener un juego por ID
- `POST /api/games` - Crear nuevo juego
- `PUT /api/games/:id` - Actualizar juego
- `DELETE /api/games/:id` - Eliminar juego

### Reseñas
- `GET /api/reviews` - Obtener todas las reseñas
- `GET /api/reviews?game=:gameId` - Obtener reseñas de un juego específico
- `POST /api/reviews` - Crear nueva reseña
- `PUT /api/reviews/:id` - Actualizar reseña
- `DELETE /api/reviews/:id` - Eliminar reseña

## 📊 Modelos de Datos

### Game
```javascript
{
  title: String,
  cover: String,
  platform: String,
  genre: String,
  status: String, // Wishlist, Playing, Completed, Abandoned
  score: Number,  // 0-5
  hoursPlayed: Number,
  createdAt: Date
}
```

### Review
```javascript
{
  game: ObjectId,
  author: String,
  text: String,
  score: Number,  // 0-5
  createdAt: Date
}
```

## 🌱 Seed Database (Opcional)

Para poblar la base de datos con datos de ejemplo:
```bash
npm run seed
```
