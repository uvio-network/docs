# Base Sepolia

<details>

<summary>Claims (UVX)</summary>

[<mark style="color:purple;">**address**</mark>](https://sepolia.basescan.org/address/0xc4E6559DBc61f59C713d8d6CD7a819c429Df076a)

```
0xc4E6559DBc61f59C713d8d6CD7a819c429Df076a
```

<mark style="color:purple;">**deployment**</mark>

```
npx hardhat ignition deploy ./ignition/modules/Claims.ts --network base-sepolia
```

<mark style="color:purple;">**arguments**</mark>

<pre><code><strong>["0xEFb36B2D443C5A6Ff4127cDa30944A12B421b9C2", "0xbf924c7081951a52c54836CB05637D8c4C77502d"]
</strong></code></pre>

<mark style="color:purple;">**verification**</mark>

```
npx hardhat verify --network base-sepolia 0xc4E6559DBc61f59C713d8d6CD7a819c429Df076a "0xEFb36B2D443C5A6Ff4127cDa30944A12B421b9C2" "0xbf924c7081951a52c54836CB05637D8c4C77502d"
```

</details>

<details>

<summary>Stablecoin</summary>

[<mark style="color:purple;">**address**</mark>](https://sepolia.basescan.org/address/0x7fc9a5730381ddf44c7d762d82a4aabc90fae786)

```
0x7FC9a5730381DdF44C7D762d82A4aabC90fAE786
```

<mark style="color:purple;">**command**</mark>

```
npx hardhat ignition deploy ./ignition/modules/Stablecoin.ts --network base-sepolia
```

<mark style="color:purple;">**arguments**</mark>

```
[6]
```

<mark style="color:purple;">**verification**</mark>

<pre><code><strong>npx hardhat verify --network base-sepolia 0x7FC9a5730381DdF44C7D762d82A4aabC90fAE786 "6"
</strong></code></pre>

</details>

<details>

<summary>UVX</summary>

[<mark style="color:purple;">**address**</mark>](https://sepolia.basescan.org/address/0xbf924c7081951a52c54836CB05637D8c4C77502d)

```
0xbf924c7081951a52c54836CB05637D8c4C77502d
```

<mark style="color:purple;">**command**</mark>

```
npx hardhat ignition deploy ./ignition/modules/UVX.ts --network base-sepolia
```

<mark style="color:purple;">**arguments**</mark>

```
["0xEFb36B2D443C5A6Ff4127cDa30944A12B421b9C2", "0x7FC9a5730381DdF44C7D762d82A4aabC90fAE786"]
```

<mark style="color:purple;">**verification**</mark>

```
npx hardhat verify --network base-sepolia 0xbf924c7081951a52c54836CB05637D8c4C77502d "0xEFb36B2D443C5A6Ff4127cDa30944A12B421b9C2" "0x7FC9a5730381DdF44C7D762d82A4aabC90fAE786"
```

</details>

