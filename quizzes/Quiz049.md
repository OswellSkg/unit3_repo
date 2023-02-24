# Task
#### Use the database bitcoin_exchange.db: and create a program that calculates the total amount of bitcoins transferred for only those transactions that are valid:


```.py
import sqlite3
from secure_password import check_password,encrypt_password

class database_worker:
    def __init__(self, name):
        self.connection = sqlite3.connect(name)
        self.cursor = self.connection.cursor()

    def search(self, query):
        result = self.cursor.execute(query).fetchall()
        return result

    def run_save(self, query):
        self.cursor.execute(query)
        self.connection.commit()

    def close(self):
        self.connection.close()

x = database_worker("bitcoin_exchange.db")
query = "SELECT * from ledger"
result = x.search(query)
x.close()

total_amount = 0

for x in result:
    string = f"id {x[0]},sender_id {x[1]},receiver_id {x[2]},amount {x[3]}"
    if check_password(string,x[4]) == True:
        total_amount += int(x[3])

    else:
        pass

print(total_amount)
```

secure_password.py:
```.py
from passlib.context import CryptContext

pwd_config = CryptContext(schemes=["pbkdf2_sha256"],
                          default="pbkdf2_sha256",
                          pbkdf2_sha256__default_rounds=30000
                          )


def encrypt_password(user_password):
    """ This function receives the plain text password from the user and returns the hash salted.
    """
    return pwd_config.encrypt(user_password)

def check_password(user_password, hashed):
    return pwd_config.verify(user_password, hashed)
```

![Screen Shot 2023-02-24 at 15 48 31](https://user-images.githubusercontent.com/112055140/221111233-3e78f3ac-9381-4f08-8d7e-a711bb8fe82c.png)

