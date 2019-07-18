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

7. `npm start`  
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

# Styling
This guide will help you how to implement Bootstrap

1. install required packages  
-- `npm i -D bootstrap @nuxtjs/style-resources`

2. setup the nuxt config file  
-- add the below code into the `nuxt.config.js` file
``` js
// Office doc: define the CSS files/modules/libraries you want to set globally
// it just used for style resources in here
// ref: https://nuxtjs.org/api/configuration-css#the-css-property 
css: ['@/assets/styles/_variables.scss', '@/assets/styles/_mixins.scss'],

// Share variables, mixins, functions across all style files
// !important Do not import actual styles.
// ref: https://github.com/nuxt-community/style-resources-module
styleResources: {
  sass: ['@/assets/styles/_variables.scss', '@/assets/styles/_mixins.scss']
},

// uncomment this line when production
// cssSourceMap: false,
```

-- add `@/plugins/styles` into `plugins`
``` js
plugins: [
  '@/plugins/styles'
],
```

-- add `@nuxtjs/style-resources` into `modules`
``` js
modules: [
  '@nuxtjs/style-resources'
],
```

3. create the plugin files  
-- create a file called `styles.js` into `plugins` folder
``` js
// the file you will put all override settings for bootstrap
import '@/assets/styles/bootstrap-override.scss'

// the files you can use for your website styles
import '@/assets/styles/global.scss'
```

4. create `bootstrap-override`  
-- create a file called `bootstrap-override.scss` into `styles` folder
``` scss
// override variables
@import "variables";

// use bootstrap
@import "node_modules/bootstrap/scss/bootstrap";
```

5. create `variables`  
-- create a file called `_variables.scss` into `styles` folder  
-- then you can add any variables here and it will override boostrap sets 
and these variables can be used in any `<style>` block in .vue file.

6. create `global`  
-- create a file called `global.scss` into `styles` folder  
-- put your global class style in here

7. create `mixins`  
-- create a file called `mixins.scss` into `style` folder  
