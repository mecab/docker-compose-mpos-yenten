Docker Compose for YTN support enabled MPOS
===========================================

**Note!** This docker-compose does **not** include `yentend` (or something coin daemon) container. Please install it by yourself beforehand.

Installation
------------
1. `cp .env.production.sample .env.production`
2. Edit `.env.production` to make it fits to your environment
3. Edit `mpos/config/*.inc.php` (especially `mpos/config/global.inc.php`) if needed.
4. Edit `stratum-mining/conf/config.py` if needed.
5. `docker-compose build && docker-compose up`
6. **(only the first time)** `docker-compose run --rm mpos /bin/install-schema && docker-compose down && docker-compose up`
7. Set [cronjobs](https://github.com/MPOS/php-mpos/wiki/Cronjobs) up.
   The scripts should run through `docker-compose exec` (`docker-compose run` could be possible, too).
   E.g. (`* * * * * docker-compose exec -T mpos /app/cronjobs/run-statistics.sh -d YTN`)

Donation
--------

- **BTC**: `1NP1LCSp8Q6YZLNSkzWAj4XmC8aJvzPJpv`
- **YTN**: `YhMqxNKFbLbVSoqhwQrWzT63ZdaMrpNd5d`
- **ZNY**: `ZrcXs55d6PCYmy2Kyh2AK24HKuXo833U6f`
