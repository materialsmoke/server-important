## supervisord
```
sudo systemctl start supervisor.service
sudo systemctl restart supervisor.service
sudo systemctl stop supervisor.service
sudo systemctl enable supervisor.service
sudo systemctl disable supervisor.service
```
#### queue job

```
[program:laravel-worker-nordicstandard-sitemap-index]
process_name=%(program_name)s_%(process_num)02d
command=php /home/alex/sitemap-index.nordicstandard.net/artisan queue:work
autostart=true
autorestart=true
user=root
numprocs=8
redirect_stderr=true
stdout_logfile= /home/alex/sitemap-index.nordicstandard.net/storage/logs/worker.log
```

#### schedule

```
[program:laravel-worker-nordicstandard-sitemap-index-schedule]
process_name=%(program_name)s_%(process_num)02d
directory=/home/alex/sitemap-index.nordicstandard.net/
command=php artisan schedule:work
autostart=true
autorestart=true
user=root
numprocs=1
redirect_stderr=true
stdout_logfile= /home/alex/sitemap-index.nordicstandard.net/storage/logs/worker1.log
```


