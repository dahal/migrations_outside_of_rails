Active Record Migrations Outside of Rails
===========================

Sample for Leveraging Active Record Migrations outside of Rails


Based on Wes Bailey's [post](http://exposinggotchas.blogspot.com/2011/02/activerecord-migrations-without-rails.html)


The Rakefile provides:

* ```rake db:migrate```
* ```rake db:rollback```

Currently the demo supports sqlite3

The db configuration is loade via ```config/databases.yml```


