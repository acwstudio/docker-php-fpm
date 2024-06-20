# Building PHP 8.0.30 Docker images
build-fpm-8.0.30:
	@echo "Building PHP 8.0.30 Docker images (linux/amd64,linux/arm64)..."
	@docker build -t php-fpm-8.0:8.0.30 -f 8.0-fpm/Dockerfile .

#########################
# Start apps containers #
#########################

# phpinfo app
start-phpinfo-8.0.30:
	@echo "Start phpinfo containers..."
	@docker compose -f web/app-phpinfo/docker-compose.yml up -d

symlink-phpinfo-8.0.30:
	cd web/app-phpinfo && \
	ln -sfn ~/Projects/test_app/phpinfo/ phpinfo
