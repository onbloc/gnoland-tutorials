In order to obtain GNOT tokens for your tests, it's often said you can **edit the genesis** file.

However if you launched `build/gnoland` locally already, you won't get any token.
That's because it starts again at whatever block it was, and at this point the genesis file isn't read anymore.

`$ gnokey query auth/accounts/g1fjh9y7ausp27dqsdq0qrcsnmgvwm6829v2au7d` 

Response:
```
height: 0
data: null
```

In order to begin at the genesis again, just remove the testdir folder and start gnoland again:

1. edit `gnoland/genesis/genesis_balances.txt` adding your address
2. `mv testdir testdir.old`
3. `build/gnoland`

Now the blockchain restarts on block 1.

`$ gnokey query auth/accounts/g1fjh9y7ausp27dqsdq0qrcsnmgvwm6829v2au7d` 

should work:
```
height: 0
data: {
  "BaseAccount": {
    "address": "g1fjh9y7ausp27dqsdq0qrcsnmgvwm6829v2au7d",
    "coins": "10000000000ugnot",
    "public_key": null,
    "account_number": "5",
    "sequence": "0"
  }
}
```
