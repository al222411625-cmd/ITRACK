# Despliegue en Render

## 1) Sube el proyecto a GitHub

Si aún no está subido:

```bash
git init
git add .
git commit -m "Primer deploy"
git branch -M main
git remote add origin https://github.com/TU_USUARIO/TU_REPO.git
git push -u origin main
```

## 2) Crea el servicio en Render

1. Abre https://render.com
2. Inicia sesión con GitHub
3. Haz clic en New > Web Service
4. Conecta el repositorio
5. Usa estas opciones:
   - Build Command: `npm install`
   - Start Command: `npm start`
   - Branch: `main`

## 3) Agrega las variables de entorno

En Render, en la sección Environment Variables, agrega estas:

```env
MONGODB_URI=tu_cadena_de_conexion_de_mongodb_atlas
MONGODB_DB=itrack
SESSION_SECRET=una_frase_secreta_muy_segura
EMAIL_USER=tu_correo@dominio.com
EMAIL_PASS=tu_contraseña_de_aplicación
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_SECURE=false
SMTP_REJECT_UNAUTHORIZED=false
```

## 4) Crea la base de datos en MongoDB Atlas

1. Abre https://www.mongodb.com/atlas
2. Crea un cluster gratis
3. Crea un usuario de base de datos
4. Autoriza accesos desde `0.0.0.0/0`
5. Copia la cadena de conexión a `MONGODB_URI`

## 5) Haz deploy

1. Haz clic en Create Web Service
2. Espera a que Render termine la instalación
3. Abre la URL pública que te proporcione

## 6) Primer acceso

Al iniciar, el sistema crea usuarios iniciales automáticamente:

- Usuario: `admin`
- Contraseña: `Admin1234`

Te recomiendo cambiar esa contraseña después de entrar.
