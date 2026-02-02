# Python-program-to-create-a-backup-of-a-SQLite-database.
import sqlite3
import io

# Connect to the SQLite database
conn = sqlite3.connect('mydatabase.db')

# Open a file to write the SQL dump
with io.open('clientes_dump.sql', 'w', encoding='utf-8') as f:
    for linha in conn.iterdump():
        f.write(f'{linha}\n')  # Corrected string formatting

print('Backup performed successfully.')
print('Saved as clientes_dump.sql')

# Close the database connection
conn.close()
