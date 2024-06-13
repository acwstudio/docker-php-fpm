# Building PHP 8.1.28 Docker images
build-fpm-8.1.28:
	@echo "Building PHP 8.1.28 Docker images (linux/amd64,linux/arm64)..."
	@docker build -t php-fpm-8.1:8.1.28 -f 8.1-fpm/Dockerfile .

#########################
# Start apps containers #
#########################

# phpinfo app
start-phpinfo-8.1.28:
	@echo "Start phpinfo containers..."
	@docker compose -f web/app-phpinfo/docker-compose.yml up -d

symlink-phpinfo-8.1.28:
	cd web/app-phpinfo && \
	ln -sfn ~/Projects/test_app/phpinfo/ phpinfo