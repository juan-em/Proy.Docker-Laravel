FROM bitnami/laravel:latest

# Copiar archivos necesarios
COPY . /app

# Configurar permisos de directorios
RUN chown -R www-data:www-data /app/storage /app/bootstrap/cache

# Instalar dependencias
RUN composer install --no-dev --optimize-autoloader --no-interaction --no-progress

# Generar llave de aplicación
RUN php artisan key:generate

# Exponer puerto
EXPOSE 80

# Iniciar servidor web
CMD ["php", "artisan", "serve", "--host=0.0.0.0", "--port=80"]