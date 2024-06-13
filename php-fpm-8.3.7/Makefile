# Building PHP 8.3.7 Docker images
build-fpm-8.3.7:
	@echo "Building PHP 8.3.7 Docker images (linux/amd64,linux/arm64)..."
	@docker build -t php-fpm-8.3:8.3.7 -f 8.3-fpm/Dockerfile .


#########################
# Start apps containers #
#########################

# phpinfo app
start-phpinfo-8.3.7:
	@echo "Start phpinfo containers..."
	@docker compose -f web/app-phpinfo/docker-compose.yml up -d

symlink-phpinfo-8.3.7:
	cd web/app-phpinfo && \
	ln -sfn ~/Projects/test_app/phpinfo/ phpinfo