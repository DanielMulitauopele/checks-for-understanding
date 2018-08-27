## Week Two - Module 2 Recap

Fork or re-pull this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON - YOU are a web developer!!!).

Note: When you're done, submit a PR.


### Week 2 Questions

1. At a high level, what is ActiveRecord? What does it do/allow you to do?

* ActiveRecord is a library(framework?) that allows you connect ruby and SQL easier. It's also know as an ORM. It can translate methods to different versions of SQL, whether that be PostgreSQL, MySQL, SQLite, etc. It allows us to interact with our databases in a relatively easy way, so we don't have to write raw SQL in our code.

2. Assume you have the following model:

```ruby
class Team << ActiveRecord::Base
end
```

What are some methods you can call on `Team`? If these methods aren't defined in the class, how do you have access to them?

* All of the methods that are defined in ActiveRecord can be used, so index, create, edit, delete, show, etc. These methods are already defined by ActiveRecord, and since this class inherits from AR, we have access to those methods. We can also use other methods that SQL uses, like join, joins, group, order, where, etc.

3. Assume that in your database, a team has the following attributes: "id", "name", owner_id". How would you find the name of a team with an id of 4? Assuming your class only included the code from question 2, how could you find the owner of the same team?

* Team.where(id: 4).name, but I'm not sure. I need to practice my ActiveRecord much more. To find the owner, we'd pull the owner_id, and we'd have to search an owner table to find the person with that primary key as an id. That's assuming the table exists though. I think it might look like:

* owner_id_var = Team.where(id: 4).owner_id
Owner.find(id: owner_id_var)

4. Assume that you added a line to your `Team` class as follows:

```ruby
class Team << ActiveRecord::Base
  belongs_to :owner
end
```

Now how would you find the owner of the team with an id of 4?

* Team.where(id: 4).owner?

5. In a database that's holding students and teachers, what will be the relationship between students and teachers? Draw the schema diagram.

* (Please see attached image in your DM's) There would be three tables, one for the students, one for the teachers, and one table called 'student_teachers' to allow a many-to-many relationship to occur. The tables would look like this, I think:

create_table "students", force: :cascade do |t|
    t.string "name"
    t.datetime "created_at", null: false
    t.datetime "updated_at", null: false
  end

create_table "teachers", force: :cascade do |t|
    t.string "name"
    t.datetime "created_at", null: false
    t.datetime "updated_at", null: false
  end

create_table "student_teachers", force: :cascade do |t|
    t.index ["student_id"], name: "index_contacts_on_company_id"
    t.index ["teacher_id"], name: "index_contacts_on_company_id"
    * (Not super sure on how this table is supposed to look?)
    t.datetime "created_at", null: false
    t.datetime "updated_at", null: false
  end

6. Define foreign key, primary key, and schema.

* Foreign key refers to the key on a table that links to the primary key of another table. Every table comes with a primary key, which is the id number of every associated row, in ascending order. If a table references another table, it will have a foreign key that corresponds to a primary key (row id) in that table. The schema is the blueprint for all of the tables in the database. It demonstrates how every table should be structured, and what columns there are, along with what the data type is for each column.

7. Describe the relationship between a foreign key on one table and a primary key on another table.

* As I've described above, the foreign key on table is referring to the primary key of another table. If I have a table called 'person' and another table called 'shoes', the 'shoes' table will have a foreign key for person. This is because this relationship is a one-to-many relationship; one person can have many pairs of shoes, but a pair of shoes typically does not belong to more than one person. If we had a table of shoes, these shoes would have a foreign key that points back to the person table and makes it possible to identify which person owns which shoes.

8. What are the parts of an HTTP response?

* Status line (with status code), Headers , Body

### Optional Questions

1. Name your five favorite ActiveRecord methods (i.e. methods your models inherit from ActiveRecord) and describe what they do.
2. Name your three favorite ActiveRecord rake tasks and describe what they do.
3. What two columns does `t.timestamps null: false` create in our database?
4. In a database that's holding schools and teachers, what will be the relationship between schools and teachers?
5. In the same database, what will you need to do to create this relationship (draw a schema diagram)?
6. Give an example of when you might want to store information besides ids on a join table.
7. Describe and diagram the relationship between patients and doctors.
8. Describe and diagram the relationship between museums and original_paintings.
9. What could you see in your code that would make you think you might want to create a partial?

### Self Assessment:
Choose One:

* I was able to answer most questions independently, but utilized outside resources for a few (I kinda feel like it's against the point for me to research the answers for questions I clearly don't know by heart. It just feels like cheating to suggest I know more than I really do. However, that's probably because I'm still used to the mod1 way of CFU's.)

Choose One:

* I feel overwhelmed by the content presented this week
