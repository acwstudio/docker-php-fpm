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

# uvi-api app
start-uvi-api-8.2.18:
	@echo "Start phpinfo containers..."
	@docker compose -f web/app-uvi-api/docker-compose.yml up -d

symlink-uvi-api-8.2.18:
	cd web/app-uvi-api && \
	ln -sfn ~/Projects/uvi/admin-api/ admin-api

# framework app
start-framework-8.2.18:
	@echo "Start phpinfo containers..."
	@docker compose -f web/app-framework/docker-compose.yml up -d

symlink-framework-8.2.18:
	cd web/app-framework && \
	ln -sfn ~/Projects/symfony/framework/ framework