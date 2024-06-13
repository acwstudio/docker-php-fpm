# Building PHP 8.2.18 Docker images
build-fpm-8.2.18:
	@echo "Building PHP 8.2.18 Docker images (linux/amd64,linux/arm64)..."
	@docker build -t php-fpm-8.2:8.2.18 -f 8.2-fpm/Dockerfile .


#########################
# Start apps containers #
#########################

# phpinfo app
start-phpinfo-8.2.18:
	@echo "Start phpinfo containers..."
	@docker compose -f web/app-phpinfo/docker-compose.yml up -d

symlink-phpinfo-8.2.18:
	cd web/app-phpinfo && \
	ln -sfn ~/Projects/test_app/phpinfo/ phpinfo