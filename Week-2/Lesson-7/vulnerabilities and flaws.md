1. In function "addNewPlayer" the state variable "num_players" will get incremented regardless of whether a new player is added, 
   since the incrementation happens outside the if condition in line 15.

2. In function "addNewPlayer" the event "winnersPaid" is emitted before any changes to state of the contract.

3. In function "pickWinner" block timestamp is used for random number generation it is unsafe since an attacker can simulate the
   block timestamp to attack the contract and add their own address to the winner list.

4. In function "payout" the If condition checks if the balance of the contract is exactly 50000000 instead of greater than. Anyone 
   can forcefully send extra ether to the smart contract thereby making this condition fail all the time.

5. The functions "pickWinner", "payout" and "distributePrize" don't have only owner modifier.

6. The "prize_winners" array is not reset after the payout. This will lead to previous prize winner also getting the share from 
   subsequent pay-outs.