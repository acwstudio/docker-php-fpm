# Building PHP 7.4.33 Docker images
build-fpm-7.4.33:
	@echo "Building PHP 7.4.33 Docker images (linux/amd64,linux/arm64)..."
	@docker build -t php-fpm-7.4:7.4.33 -f 7.4-fpm/Dockerfile .

#########################
# Start apps containers #
#########################

# phpinfo app
start-phpinfo-7.4.33:
	@echo "Start phpinfo containers..."
	@docker compose -f web/app-phpinfo/docker-compose.yml up -d

symlink-phpinfo-7.4.33:
	cd web/app-phpinfo && \
	ln -sfn ~/Projects/test_app/phpinfo/ phpinfo