# Help with Artisan commands:

Serve the application: `php artisan serve`

Make a model, migration & controller: `php artisan make:model <name> --controller --migration`. Can use `--resource` instead of `--controller` to make a resource controller.

List all routes: `php artisan route:list`

Seed Database: `php artisan db:seed`

Migrate: `php artisan migrate`. Migrate:refresh will rollback all migrations then execute migrate command. Migrate:refresh will drop all tables and run migration (NOT ADVISED IN PRODUCTION).

Make a API controller, excludes the create and edit methods: `php artisan make:controller <name> --api`.
