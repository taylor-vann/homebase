# Auth

quick, local, authorization and authentication

## features

- people
- passwords
- sessions
- ratelimits
- roles

## people

The `people` table is defined as:

```
id INT64
username VARCHAR(320)
password VARCHAR(256)
password_params VARCHAR(256)
is_deleted BOOLEAN
```

## sessions

The `sessions` table (also could reside solely in `redis` table).

The `session` is made up of a random 256 bit number.

```
id INT64
session uint256
user_id int64
roles VARCHAR(256)
is_deleted BOOLEAN
```

## ratelimits

Ratelimits exist in-memory.

`type` for different endpoints, for instance streaming media might need more requests
than static media.

```
id <session_id, type>
count int8
```

## roles

`roles` define access to resources

```
id int16
role VARCHAR(32)
is_deleted BOOLEAN
```

## contact info

stretch goal:

contact info defined as:

`devices`

```
id INT64
user_id INT64
navigator VARCHAR(512)
device VARCHAR(128)
is_deleted BOOLEAN
```

`phone`

```
id INT64
user_id INT64
number VARCHAR(32)
is_deleted BOOLEAN
```

`email`

```
id INT64
user_id
email VARCHAR(320)
is_deleted BOOLEAN
```

