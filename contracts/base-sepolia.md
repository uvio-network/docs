# Base Sepolia

<details>

<summary>Claims (UVX)</summary>

[<mark style="color:purple;">**address**</mark>](https://sepolia.basescan.org/address/0x48455E0c620D46239BE9358C9B2Bd6D0bf1F3AA6)

```
0x48455E0c620D46239BE9358C9B2Bd6D0bf1F3AA6
```

<mark style="color:purple;">**deployment**</mark>

```
npx hardhat ignition deploy ./ignition/modules/Claims.ts --network base-sepolia
```

<mark style="color:purple;">**arguments**</mark>

<pre><code><strong>["0xEFb36B2D443C5A6Ff4127cDa30944A12B421b9C2", "0x04Ec0582e2700Db583e3BCb9b913D181Ac2D68A8"]
</strong></code></pre>

<mark style="color:purple;">**verification**</mark>

```
npx hardhat verify --network base-sepolia 0x48455E0c620D46239BE9358C9B2Bd6D0bf1F3AA6 "0xEFb36B2D443C5A6Ff4127cDa30944A12B421b9C2" "0x04Ec0582e2700Db583e3BCb9b913D181Ac2D68A8"
```

[<mark style="color:purple;">**version**</mark>](https://github.com/uvio-network/contracts/blob/v0.2.0/contracts/Claims.sol)

```
v0.2.0
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

[<mark style="color:purple;">**address**</mark>](https://sepolia.basescan.org/address/0x04Ec0582e2700Db583e3BCb9b913D181Ac2D68A8)

```
0x04Ec0582e2700Db583e3BCb9b913D181Ac2D68A8
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
npx hardhat verify --network base-sepolia 0x04Ec0582e2700Db583e3BCb9b913D181Ac2D68A8 "0xEFb36B2D443C5A6Ff4127cDa30944A12B421b9C2" "0x7FC9a5730381DdF44C7D762d82A4aabC90fAE786"
```

[<mark style="color:purple;">**version**</mark>](https://github.com/uvio-network/contracts/blob/v0.2.0/contracts/UVX.sol)

```
v0.2.0
```

</details>

