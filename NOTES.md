#ActiveRecord Jr. vs ActiveRecord
<pre>
10 mins : contextualizing AR Jr. wrt AR
  - AR Query interface, look how similar it is...
  - Rakefile ... let's ask "can we get rid of this SQL "... migrations
  - "how would you check a valid format for email?" ... AR validations
</pre>


##Let's compare!

* [activerecord-jr-1-a-basic-orm-challenge/blob/master/source/activerecord_jr/models/cohort.rb](https://github.com/purple-martins-2014/activerecord-jr-1-a-basic-orm-challenge/blob/master/source/activerecord_jr/models/cohort.rb)
* [RoR/active_record_querying.html](http://guides.rubyonrails.org/active_record_querying.html)

##SQL in The Rakefile

* [activerecord_jr/Rakefile]()
  * Challenges?   

##Data Integrity

* Create a new Student
  * Empty fields?
  * Format of email? 

#Active Record Migrations

* [RoR/migrations.html](http://guides.rubyonrails.org/migrations.html)

###Creation Examples:
<pre>
15 mins : focus on `create` migrations
  - intro top conventions (file names, etc)
  - run through 1-2 examples
  - show the effect on the .schema
</pre>

_db/migrate/20140708043852_create_products.rb_

```
class CreateProducts < ActiveRecord::Migration
  def change
    create_table :products do |t|
      t.string :name
      t.text :description
      t.integer :price
      t.timestamps
    end
  end
end
```

_db/migrate/20140708052149_create_categories.rb_

```
class CreateCategories < ActiveRecord::Migration
  def change
    create_table :categories do |t|
      t.string :name
      t.timestamps
    end
  end
end
```

###Change Examples:
<pre>
5 mins : quick intro to a change
  - add a column, rename a field, something like that
</pre>

_db/migrate/20140708052212_add_category_to_products.rb_

```
class AddCategoryToProducts < ActiveRecord::Migration
  def change
    add_reference :products, :category, index: true
  end
end
```

_db/migrate/20140708200301_rename_category_name_to_title.rb_

```
class RenameCategoryNameToTitle < ActiveRecord::Migration
  def change
     change_table :categories do |t|
       t.rename :name, :title
     end
  end
end
```

#Active Model Validations

<pre>
15 mins : focus on validations
  - walk through of guides
  - optionally demo errors
</pre>

* [RoR/active_record_validations.html](http://guides.rubyonrails.org/active_record_validations.html)

