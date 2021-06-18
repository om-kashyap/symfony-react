# Building a single page with Symfony and React



```bash
git clone git@github.com:berymo/symfony-react.git
```

The preceding command will install the new Symfony application successfully on your computer.


## Start the application

Start the application using the built-in Symfony PHP web server by changing directory into the newly created project. Run the following command to start the application:

```bash
// Change directory
cd symfony-react-project

// Start the server
php bin/console server:run
```

Open your browser and navigate to `http://localhost:8000` to view the welcome page. The version displayed here is the current one for Symfony at the time of writing, which might not be the same as yours:


![](https://paper-attachments.dropbox.com/s_1265725ADB054532A55C0EFD08DF0FAB2CEE8562C503298703A715DFE50C9E5D_1563630485394_symfony-react-home.png)



Next, you can test the backend API using [Postman](https://www.getpostman.com/). Start the application again from the terminal using the development server by running `php bin/console server:run`. Next, try accessing the user list endpoint on http://localhost:8000/api/users. You will see the list of users as show here:


![](https://paper-attachments.dropbox.com/s_1265725ADB054532A55C0EFD08DF0FAB2CEE8562C503298703A715DFE50C9E5D_1563644901996_symfony-users.png)


At the moment, we have successfully setup the Symfony application. In the next section, we will start building the frontend with React.


## Building the Frontend App with React

To successfully setup the React application, we will install Symfony Webpack Encore. To begin, open another terminal and run the following command to install Webpack Encore using Composer. Make sure you are still in the project directory.

```bash
composer require symfony/webpack-encore-bundle
```

followed by:

```
yarn install
```

The command above will create a `webpack.config.js` file, an `assets` folder and add `node_modules` folder to the `.gitignore` file.

Once the installation process is complete, use Yarn to install React, React-router, [Axios](https://github.com/axios/axios) and other dependencies.

```
yarn add @babel/preset-react --dev
yarn add react-router-dom
yarn add --dev react react-dom prop-types axios
yarn add @babel/plugin-proposal-class-properties @babel/plugin-transform-runtime
```


## Running your React and Symfony App

Now, run the application and test its functionality. Before that, ensure that both the Symfony and React application are currently running from separate terminals within your project directory. In case you have closed it already use the command below to resume the Symfony application:

```bash
php bin/console server:run
```

And from the second terminal, run the following command to compile the React application and watch the JavaScript files for any changes:

```bash
yarn encore dev --watch
```

Navigate to `http://localhost:8000` to view the list of users:


![](https://paper-attachments.dropbox.com/s_1265725ADB054532A55C0EFD08DF0FAB2CEE8562C503298703A715DFE50C9E5D_1563647884397_list-users.png)


Next, click on **Posts** from the navigation bar to view the list of posts fetched from the [JSONPlaceholder](https://jsonplaceholder.typicode.com/):


![](https://paper-attachments.dropbox.com/s_1265725ADB054532A55C0EFD08DF0FAB2CEE8562C503298703A715DFE50C9E5D_1563647978911_post-list.png)
