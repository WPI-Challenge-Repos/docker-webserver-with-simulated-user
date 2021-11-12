# About

This repository contains the code for launching a docker container running
Apache and a simulated user. This setup is useful for creating CTF challenges
that rely on attackers manipulating the browser behavior of a victim
user/admin, e.g., XSS attacks.  

By default, this user makes a `GET` request to
localhost every 10 seconds for up to 1 hour.  To change the url or frequency
used by the simulated user, you'll need to modify `run_user.py`. It should also
be possible to modify this simulated user to do more complex tasks, such as
clicking on a specific link in the target page.


# Troubleshooting

The `chromedriver` executable is tied to a specific version of chrome. It is
possible that the chromedriver downloaded by the Dockerfile in this repo will
stop working.  

You can view the Apache access log by running: `docker exec CONTAINER cat
/var/log/apache2/access.log`
