```
$ cargo install cargo-contract

$ cargo contract build
 [1/*] Building cargo project
    Finished release [optimized] target(s) in 0.09s

The contract was built in DEBUG mode.

Your contract artifacts are ready. You can find them in ./target/ink:

  - erc20.contract (code + metadata)
  - erc20.wasm (the contract's code)
  - erc20.json (the contract's metadata)

$ cargo contract upload --suri //Bob --url wss://rococo-contracts-rpc.polkadot.io -x --verbose
      Events
       Event Balances ➜ Withdraw
         who: 5FHneW46xGXgs5mUiveU4sbTyGBzmstUspZC92UhjJM694ty
         amount: 704.530206μROC
       Event Contracts ➜ CodeStored
         code_hash: 0xe9fd84e04e71315476b248929634ae04d521dcb6e4fe89d492e6f1a4b8b02b76
         deposit_held: 2.034559641mROC
         uploader: 5FHneW46xGXgs5mUiveU4sbTyGBzmstUspZC92UhjJM694ty
       Event Balances ➜ Deposit
         who: 5EYCAe5cKPAoFh2HnQQvpKqRYZGqBpaA87u4Zzw89qPE58is
         amount: 704.530206μROC
       Event TransactionPayment ➜ TransactionFeePaid
         who: 5FHneW46xGXgs5mUiveU4sbTyGBzmstUspZC92UhjJM694ty
         actual_fee: 704.530206μROC
         tip: 0ROC
       Event System ➜ ExtrinsicSuccess
         dispatch_info: DispatchInfo { weight: Weight { ref_time: 2463698560, proof_size: 3607 }, class: Normal, pays_fee: Yes }

   Code hash "0xe9fd84e04e71315476b248929634ae04d521dcb6e4fe89d492e6f1a4b8b02b76"

$ cargo contract instantiate --suri //Bob --url wss://rococo-contracts-rpc.polkadot.io --constructor new --args 10000000 -x --verbose
 Dry-running new (skip with --skip-dry-run)
    Success! Gas required estimated at Weight(ref_time: 1388187817, proof_size: 24530)
Confirm transaction details: (skip with --skip-confirm)
 Constructor new
        Args 10000000
   Gas limit Weight(ref_time: 1388187817, proof_size: 24530)
Submit? (Y/n): 
      Events
       Event Balances ➜ Withdraw
         who: 5FHneW46xGXgs5mUiveU4sbTyGBzmstUspZC92UhjJM694ty
         amount: 715.453529μROC
       Event System ➜ NewAccount
         account: 5FjbbVym8brgzM49p628j1kn4r8FnrMLz8natjMwEkDo8sCd
       Event Balances ➜ Endowed
         account: 5FjbbVym8brgzM49p628j1kn4r8FnrMLz8natjMwEkDo8sCd
         free_balance: 3.333333μROC
       Event Balances ➜ Transfer
         from: 5FHneW46xGXgs5mUiveU4sbTyGBzmstUspZC92UhjJM694ty
         to: 5FjbbVym8brgzM49p628j1kn4r8FnrMLz8natjMwEkDo8sCd
         amount: 3.333333μROC
       Event Contracts ➜ ContractEmitted
         contract: 5FjbbVym8brgzM49p628j1kn4r8FnrMLz8natjMwEkDo8sCd
         data: Transfer { from: None, to: Some(5FHneW46xGXgs5mUiveU4sbTyGBzmstUspZC92UhjJM694ty), value: 10000000 }
       Event Contracts ➜ Instantiated
         deployer: 5FHneW46xGXgs5mUiveU4sbTyGBzmstUspZC92UhjJM694ty
         contract: 5FjbbVym8brgzM49p628j1kn4r8FnrMLz8natjMwEkDo8sCd
       Event Contracts ➜ StorageDepositTransferredAndHeld
         from: 5FHneW46xGXgs5mUiveU4sbTyGBzmstUspZC92UhjJM694ty
         to: 5FjbbVym8brgzM49p628j1kn4r8FnrMLz8natjMwEkDo8sCd
         amount: 1.281101179mROC
       Event Contracts ➜ StorageDepositTransferredAndHeld
         from: 5FHneW46xGXgs5mUiveU4sbTyGBzmstUspZC92UhjJM694ty
         to: 5FjbbVym8brgzM49p628j1kn4r8FnrMLz8natjMwEkDo8sCd
         amount: 1.334399976mROC
       Event Balances ➜ Deposit
         who: 5FHneW46xGXgs5mUiveU4sbTyGBzmstUspZC92UhjJM694ty
         amount: 5.446334μROC
       Event Balances ➜ Deposit
         who: 5EYCAe5cKPAoFh2HnQQvpKqRYZGqBpaA87u4Zzw89qPE58is
         amount: 710.007195μROC
       Event TransactionPayment ➜ TransactionFeePaid
         who: 5FHneW46xGXgs5mUiveU4sbTyGBzmstUspZC92UhjJM694ty
         actual_fee: 710.007195μROC
         tip: 0ROC
       Event System ➜ ExtrinsicSuccess
         dispatch_info: DispatchInfo { weight: Weight { ref_time: 5795419991, proof_size: 16938 }, class: Normal, pays_fee: Yes }

    Contract 5FjbbVym8brgzM49p628j1kn4r8FnrMLz8natjMwEkDo8sCd
```
