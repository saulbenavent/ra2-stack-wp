# Decisión de imagen y versión del CMS (WordPress)

## Requisitos oficiales de WordPress
- **PHP:** Versión recomendada 7.4+ / 8.1+
- **Base de Datos:** MariaDB 10.5+ o MySQL 8.0+
- **HTTPS:** Recomendado / Exigido para un entorno seguro

## Decisión de la imagen de Docker
- **Imagen elegida:** `wordpress:7.1-php8.3-fpm` (o la variante `-php8.3-fpm` más reciente disponible)

### Cuestiones analizadas:
1. **Diferencia entre `-apache` y `-fpm`:**
   - `-apache`: Incluye el servidor web Apache y PHP juntos.
   - `-fpm`: Solo incluye PHP (más ligero y rápido), pero requiere un proxy inverso (como Nginx o Apache en otro contenedor).
2. **Significado de `php8.3`:**
   - Indica la versión de PHP integrada en la imagen.
3. **¿Por qué no usar `latest`?**
   - Porque cambia con el tiempo y puede meter actualizaciones que rompan el proyecto sin aviso previo.
