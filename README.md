# NuxtJS in Homestead
Guide of testing NuxtJS SSR in homestead environment

Follow the below steps to test the NuxtJS app in server side environment

1. `homestead ssh`  
-- enter to your vm

2. `npm install`  
-- install required packages

3. `npm run build`  
-- build application

4. `sudo nano /etc/nginx/sites-available/dch-nuxt.test` or using `vim`
-- edit the nginx configuration

5. copy [this file](./nginx-config), and change the `server_name` value. Then, replace into the step 4 config file

6. `sudo service nginx reload`
-- reload the nginx service

7. `npm start &`
-- start the app, done

# Create NuxtJS Project

1. `npx create-nuxt-app <project-name>`
-- create your project with name

2. `Express`
-- choose Express as custom server framework

3. `Axios`
-- install Axios as Nuxt.js modules

4. `ESLint`
-- choose ESLint as linting tools

5. `Universal (SSR)`
-- choose Universal (SSR) as rendering mode