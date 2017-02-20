## This is a demonstration of the basic full SPA react setup.  

### The goal of the app is to provide a convention for React + Rails Combo.   

There are two types of apps in Netguru(source: Pavel "Gdański Koksu" Jędrzejczyk).  
One type is full SPA app, and this repo is the representation of it's initial setup.

# To scaffold an app:  

```text
npm i -g create-react-app  
rails new netguruSPA --api  
git init  
create-react-app client  
echo "client/node_modules” >> .gitignore  
echo "gem 'foreman'" >> Gemfile  
bundle install  
touch Procfile  
echo "api: bundle exec rails s -p 3000” >> Procfile  
echo "web: cd client && npm start" >> Procfile  
touch lib/tasks/start.rake  
```

Add to lib/tasks.start.rake:  
```ruby
task :start do  
  exec 'foreman start -p 3000'  
end
```

Add to head tag in client/public/index.html(only if using react-bootstrap or bootstrap):  
```html
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/latest/css/bootstrap.min.css">  
```

Add to package.json:
```text
 "proxy": "http://localhost:3000/,  
```

Install frontend related dependencies:
```text
cd client && npm i dotenv i18n-js lodash moment redux react-redux redux-form redux-saga react-router react-router-redux react-datepicker react-bootstrap --S  
```

And lastly:
```text
npm i ava --D  
```


Cd to top folder and run:  
```text
rake start
```

If everything works do:  
```text
Git add .  
Git commit -m "Init NetguruSPA”  
```

### Any suggestions, be it milestones, folder structure or dependencies are very welcome.
