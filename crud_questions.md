# CRUD Quiz

Use the solution to this afternoon's Property Tracker lab to answer the following questions. Please write your answers under each question, push the file to GitHub, and submit in the usual way.

## MVP Questions

In our Property Tracker application:

Q1. Where are we instantiating instances of the `Property` class?

in property.rb at the beginning.
def initialize
...
end

Q2. Where are we defining the SQL that enables us to save the ruby `Property` object into the database?
in properties.sql

Q3. In console.rb, which lines modify the database?
under

def save()
end

and

def
update()
end

Q4. Why do we not define the id of a `Property` object at the point we instantiate it (‘new it up’)?
Because we need to let the db generate the id. Since we do not know which numbers the db will generate for which item and it might mess things up.

Q5. Where and how do we assign the id (that is generated by the database) to the ruby `Property` object?
it is done in the save method
@id = db.exec_prepared("save", values)[0]['id'].to_i  #don't forget to execute the method!

and then it needs to be instantiated in def initialize...
@id = options['id'].to_i if options['id']

Q6. Why do we put a guard (an `if` clause) on the `@id` attribute in the constructor?
--

Q7. Why are some of the CRUD actions represented by instance methods, and others by class methods?
--

Q8. What type of data structure is returned by calls to `db.exec_prepared()`? In the `save` method, how do we access the id from the returned data structure?
intenger

Q9. Why do we use prepared statements when performing database operations?
to protect the db from user entries which might delete or make fatal changes. sanitize db.

## Extension Questions

Look at the `find_by_id` and `find_by_address` methods in the `Property` class.

Q10. What do they take in as their arguments?

Q11. What are their return values?
arrays
