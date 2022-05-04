# Code review checklist

`// SPDX-License-Identifier: MIT`
`pragma solidity ^0.8.13;`

- [ ] Use custom errors
`if (msg.value !== valAccumulator) revert ValueMismatch();`

- [ ] Use `abstract contract`s to reuse code

- [ ] Install dependencies with specific version tags
`forge install OpenZeppelin/openzeppelin-contracts@v4.6.0`

- [ ] Name variables following conventions
`address dai;` not `address Dai;`

- [ ] Give meaningful variable names
`bytes32 pkx = "pkx";` instead of `bytes32 test = "test";`

- [ ] Use helper methods in the libraries you installed
Instead of
`stdstore.target(Dai).sig(IERC20(token).balanceOf.selector).with_key(address(this)).checked_write(1000*1e18);` use `tip()`

- [ ] Remove unused variables

- [ ] Remove unnecessary and outdated comments

- [ ] Use existing contract names instead of `testContract`

- [ ] Specify uint size
`uint256` instead of `uint`

- [ ] Set VScode tab size to 2

- [ ] Enable *Trim Trailing Whitespace*

- [ ]  Use more rigorous assertions
`expectCall` and `expectEmit` instead of `AssertEq`

- [ ] Test with realistic and reasonable amounts of var values

- [ ]  Read existing values from the contract *sometimes*

- [ ] Setup and reuse w/ `super.setUp()`

- [ ] Avoid repetitive variable declerations

- [ ] Create an internal fn without checks and an external one that calls the internal fn with all the cheks *sometimes*

- [ ] Use `safeTransferFrom` and `safeApprove`

- [ ] Cast var types instead of new vars ex. `address(token)`

- [ ] Take an address in the constructor for more flexibility

- [ ] Avoid temporary variables that are only used once within functions

- [ ] Call vars `sender` instead of `caller` and `amount` instead of `value`

- [ ] Emit events efficiently

- [ ] Use internal pure methods when repeated logic is involved

- [ ] Make sure up-casting isn't the reason errors are being thrown
Use up-casting ex. `uint256 total = uint256(amount) + amoun2`

- [ ] Create post Setup tests if needed

- [ ] Prefix with "I" when calling interfaces, ex. `IExample`

- [ ] Prefix argument variables with "_" where needed

- [ ] Use Interface over others. Among others use `abi.encodeWithSelector()` above the rest.

- [ ] Use `abi.encodePacked` if you don't know the sig/calldata until runtime. You can also use `abi.encodeWithSignature`

- [ ] Use 0xEeeeeEeeeEeEeeEeEeEeeEEEeeeeEeeeeeeeEEeE to represent Ether

- [ ] Original commenter resolves the comments on Github!

- [ ] verify the `msg.value == accumulator` to avoid excess ETH getting stuck
