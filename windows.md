

# CHROME 

## File Location 
APPDATA\\Local\\Google\\Chrome\\User Data\\Default\\Login Data


## File Format 
SQLLite 

## PASSWORD ENCRYPTION 
CryptProtectData, which is a Windows API function for encrypting data. Data encrypted with this function is pretty solid. It can only be decrypted on the same machine and by the same user that encrypted it in the first place.

### DECRYPTION ALGORITHM EXAMPLE 

cursor.execute('SELECT action_url, username_value, password_value FROM logins')
for result in cursor.fetchall():
    password = win32crypt.CryptUnprotectData(result[2], None, None, None, 0)[1]


 
