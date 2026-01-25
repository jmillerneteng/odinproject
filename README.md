# odinproject and nginx

# installing NGINX on ubuntu for remote web testing
[reference docs](https://ubuntu.com/tutorials/install-and-configure-nginx#3-creating-our-own-website)
  install `sudo apt install nginx

[ref video](https://www.youtube.com/watch?v=XcSFqwzNYkA) for virtual server configurations

#notes on dir structure
html config files are stored in /var/www/
server config files are created in /etc/nginx/conf.d/

#symlink dir to /var/www 
ln -s /home/jon/gh_repos/dir /var/www/{servername}.local << be sure to use full path

#fix permissions for nginx/www-data to access files from symlink source
sudo usermod -aG yourusername www-data << add my account to www-data seems cleaner
chown -R yourusername:www-data /home/yourusername/your-project-dir << changes ownership of the foler/project

#t-shooting
tail -f /var/log/nginx/error.log

to allow for symlinks modified the /etc/nginx/nginx.conf 
`disable_symlinks off;`
