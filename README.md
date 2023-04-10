# Cerys
Erm
import sqlite3

# create a connection to the database
conn = sqlite3.connect('example.db')

# create a cursor to execute database queries
c = conn.cursor()

# create a table to store entities
c.execute('''CREATE TABLE entities
             (id INTEGER PRIMARY KEY AUTOINCREMENT,
              name TEXT NOT NULL,
              email TEXT NOT NULL)''')

# add an entity to the table
c.execute("INSERT INTO entities (name, email) VALUES ('John Doe', 'johndoe@example.com')")

# retrieve all entities from the table
c.execute("SELECT * FROM entities")
print(c.fetchall())

# update an entity in the table
c.execute("UPDATE entities SET name='Jane Doe' WHERE id=1")

# delete an entity from the table
c.execute("DELETE FROM entities WHERE id=1")

# commit the changes to the database
conn.commit()

# close the database connection
conn.close()
