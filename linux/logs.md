# Logs

## Connexion

```
less /var/log/auth.log
```
*10 last line*
```
tail /var/log/auth.log
```
*Streaming*
```
tail -f /var/log/auth.log
```

## Users groups
*file for all users, the :x: is password*
```
cat /etc/passwd
```
*Password*
```
cat /etc/shadow
```
*file for groups*
```
cat /etc/group
```