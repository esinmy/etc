# Curl for sending email #
```
curl \
  --url 'smtp://smtp-address:587' \
  --user 'username:password' \
  --mail-from 'username@gmail.com' \
  --mail-rcpt 'john@example.com' \
  --mail-rcpt 'to2@domain.com' \
  --upload-file mail.txt \
  --verbose
```

`From` and `To` in `mail.txt` are just data; they are responsible for displaying but do not relate to real sender and recipient.

*Reference:*

https://stackoverflow.com/questions/14722556/using-curl-to-send-email