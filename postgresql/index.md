# PostgreSQL


&laquo; [Back to index](https://github.com/janelznic/cheatsheets)

### Database Maintenance
* Login as postgres user ```sudo su postgres```
* Create a new user ```createuser robotics```
* Create a database fulfillment and grant privilegies for robotics ```createdb fulfillment -O robotics```
* Go to interactive mode ```psql```
* List databases ```\l```
* Use database ```\c fulfillment```
* Drop schema & cascade ```DROP SCHEMA inventary CASCADE;```
* Show help ```\?```
* Quit interactive mode ```\q```
