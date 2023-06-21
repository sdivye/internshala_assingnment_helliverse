# Heliverse_project

## To Deploy React JS on Root Domain (xtended.live )

Follow the steps below to deploy a React application on the root domain:

1. Clone the React application repository from GitHub.

2. Install the required dependencies and build the React application.

3. Configure the Nginx web server:
   - Edit the Nginx configuration file for the "xtended.live " domain.
   - Include the reverse proxy settings to route requests to the React application.

4. Test the Nginx configuration:
   - Verify the Nginx configuration to ensure it is error-free.

5. Restart the Nginx web server:
   - Apply the changes by restarting the Nginx service.

6. Configure DNS settings for the domain:
   - Associate the "xtended.live " domain with the server's IP address.
   - In the DNS settings, add an "A" record that points the "xtended.live " domain to the server's IP address.

7. Wait for DNS propagation:
   - After making the DNS changes, allow time for the changes to propagate across the DNS network.

8. Access the React application:
   - Once the DNS propagation period is over, visit "xtended.live " in a web browser.
   - The React application should be accessible on the root domain.




## Deploying AngularJS on a Subdirectory of the Domain (xtended.live /dashboard)

Follow the steps below to deploy an AngularJS application on a subdirectory of the domain:

1. Clone the AngularJS application repository from GitHub.

2. Install the necessary dependencies and build the AngularJS application.

3. Copy the built files to the target directory:
   - Copy the built files from the AngularJS application to the `/var/www/html/dashboard` directory.
   - This directory will serve as the root directory for the "xtended.live /dashboard" URL.

4. Configure the Nginx web server:
   - Edit the Nginx configuration file for the "xtended.live " domain.
   - Add a location block to handle requests to the "xtended.live/dashboard" URL.
   - Specify the root directory as `/var/www/html/dashboard` in the Nginx configuration.

5. Restart the Nginx web server:
   - Apply the changes by restarting the Nginx service.

6. Configure DNS settings for the domain:
   - Associate the "xtended.live " domain with the server's IP address.
   - In the DNS settings, add a CNAME record or an A record with "dashboard" as the subdomain.
   - Point the CNAME or A record to the IP address of the server where the AngularJS application is deployed.

7. Wait for DNS propagation:
   - After making the DNS changes, allow time for the changes to propagate across the DNS network.

8. Access the AngularJS application:
   - Once the DNS propagation period is over, visit "xtended.live /dashboard" in a web browser.
   - The AngularJS application should be accessible on the subdirectory URL.



## Deploying Spring Boot Application on Subdirectory of Domain

1. Clone the Spring Boot application repository from GitHub.

2. Build the application and copy the generated files to the `/var/www/html/` directory. This directory will serve as the root directory for your application.

3. Configure the Nginx web server:
   - Edit the Nginx configuration file for the "xtended.live " domain or the "spring.xtended.live " subdomain.
   - Add a location block in the Nginx configuration to handle requests for your application's URL.
   - Set the root directory as `/var/www/html/` in the Nginx configuration.

4. Test the Nginx configuration:
   - Verify the Nginx configuration to ensure there are no errors.

5. Configure DNS settings for the domain or subdomain:
   - Add a CNAME record or an A record for the "spring" subdomain in the DNS settings.
   - Point the record to the IP address of the server where the Spring Boot application is deployed.

6. Wait for DNS propagation:
   - Allow time for the DNS changes to propagate across the network.

7. Access the Spring Boot application:
   - After the DNS propagation period, visit "spring.xtended.live " in a web browser.
   - Your Spring Boot application should be accessible on the specified subdirectory of the domain.

8. Run the Spring Boot application in the background:
   - Use the `nohup` command to start the application and detach it from the current terminal session.
   - Run `nohup java -jar spring-boot-web.jar &` to start the application.

9. Optional: Monitor the application's output:
   - Use the nano editor to view the `nohup.out` file and monitor the application's output and error messages.

10. Restart the Nginx web server:
    - Restart the Nginx service using the command `systemctl restart nginx`.



