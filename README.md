docker build .

docker-compose build

docker-compose run --rm app sh -c "django-admin startproject app ."

docker-compose run --rm app sh -c "django-admin startapp [app_name]"

docker-compose run --rm app sh -c "python manage.py test"

docker-compose run --rm app sh -c "flake8"

docker-compose run --rm app sh -c "python manage.py test && flake8"

docker-compose run --rm app sh -c "python manage.py makemigrations"

docker-compose run --rm app sh -c "python manage.py createsuperuser"

docker-compose run --rm app sh -c "python manage.py wait_for_db && python manage.py migrate"
If you get "InconsistentMigrationHistory" error after migrate, clear the db data on volumes:
docker volume rm [volume_name]
To see all volume names:
docker volume ls
Choose the one used by your current project.
If you get "volume is in use" error when deleting the volume, shut it down:
docker-compose down

To automatically trim whitespaces on VSCode:
Code (top left) > Preferences > Settings,
Search for: "Trim Trailing Whitespace"
Check the checkbox.

Superusers:
admin@example.com (pass: Bakmigondrong)