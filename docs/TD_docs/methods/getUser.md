---
title: getUser
description: Returns information about a user by its identifier, offline request if current user is not a bot
---
## Method: getUser  
[Back to methods index](index.md)


Returns information about a user by its identifier, offline request if current user is not a bot

### Params:

| Name     |    Type       | Required | Description |
|----------|:-------------:|:--------:|------------:|
|user\_id|[int](../types/int.md) | Yes|User identifier|


### Return type: [User](../types/User.md)

### Example:


```
$MadelineProto = new \danog\MadelineProto\API();
if (isset($token)) { // Login as a bot
    $this->bot_login($token);
}
if (isset($number)) { // Login as a user
    $sentCode = $MadelineProto->phone_login($number);
    echo 'Enter the code you received: ';
    $code = '';
    for ($x = 0; $x < $sentCode['type']['length']; $x++) {
        $code .= fgetc(STDIN);
    }
    $MadelineProto->complete_phone_login($code);
}

$User = $MadelineProto->getUser(['user_id' => int, ]);
```

Or, if you're into Lua:

```
User = getUser({user_id=int, })
```

