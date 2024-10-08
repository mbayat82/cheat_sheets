### Date Basics
`from datetime import date`

```
today = date.today()
print (today)
2024-08-18
```

```
print(today.day)
18
print(today.month)
8
print(today.year)
2024
```

### Date Formats
For months
```
print(today.strftime("%B"))
August

print(today.strftime("%b"))
Aug
```

For days
```
print(today.strftime("%A"))
'Sunday'
print(today.strftime("%a"))
'Sun'
```

Full documentation [here](https://docs.python.org/3/library/datetime.html#strftime-and-strptime-format-codes)

### Date and Time Basics
`from datetime import datetime`

```
now = datetime.now()
print(now)
2024-08-18 13:14:45.427295
```

### Date/Time Formats
```
print(now.hour)
13

print(now.minute)
14

print(now.second)
45

print(now.month)
8
```

### Load Date/Time
```
ch_date = datetime.fromisoformat("1986-04-26 01:23:40:000+04:00")
```

### Substract Date/Time
```
now = datetime.now()
now2 = datetime.now()
a = now2 - now
print(a)
0:00:18.645351
```
Note that the returned value is a timedelta format, which only has day, seconds, and microseconds.