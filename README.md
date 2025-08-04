⚡ Solidity VS Code Snippets – Smart Contract Boilerplate
This collection of Visual Studio Code snippets is designed to supercharge your Solidity smart contract development. Quickly scaffold common patterns like contract skeletons, modifiers, access control, and ERC20 interactions using simple prefix shortcuts.

🛠 Installation
Open VS Code

Press Cmd+Shift+P (Mac) / Ctrl+Shift+P (Windows)

Choose Preferences: Configure User Snippets

Select New Global Snippets file or Solidity language

Paste the JSON snippet content into the file

Save and start using the snippets in .sol files!

🔖 Snippets Overview
🧱 Contract Structure
Prefix	Description
contract	Basic contract skeleton with constructor
constructor	Constructor with immutable owner setup
onlyowner	Access control modifier (onlyOwner)
fonlyowner	Function with onlyOwner modifier

🧩 Functions
Prefix	Description
fpub	Public function template
fext	External function
fint	Internal function
fpriv	Private function
fview	View function
fpure	Pure function
fpay	Payable function
freceive	Receive function (ETH fallback)
ffallback	Fallback function
fmod	Function with modifier

🔐 Access & Errors
Prefix	Description
error	Declare custom Solidity error
revert	Revert using a custom error

🧾 Events
Prefix	Description
event	Event declaration
emit	Emit an event

🤝 Interfaces & ERC20
Prefix	Description
interface	Interface definition
erc20reads	Read helper functions for ERC20 (balance, allowance)
safetransfer	ERC20 token transfer snippet

🧮 SafeMath (for older Solidity)
Prefix	Description
safemath	Example using SafeMath lib

🔍 Example Usage
Contract Skeleton (contract)

solidity

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.19;

contract MyContract {
    address public owner;

    constructor() {
        owner = msg.sender;
    }
}
Only Owner Modifier + Function (onlyowner + fonlyowner)

solidity

modifier onlyOwner() {
    require(msg.sender == owner, "Not owner");
    _;
}

function updateValue(uint256 _value) public onlyOwner {
    // logic here
}
ERC20 Read (erc20reads)

solidity

IERC20 public token;

function balanceOf(address user) external view returns (uint256) {
    return token.balanceOf(user);
}

function allowanceOf(address owner, address spender) external view returns (uint256) {
    return token.allowance(owner, spender);
}
🤝 Contribution
Want to expand this collection? PRs and suggestions welcome:

Add common patterns (Ownable, Pausable, etc.)

Add advanced templates (upgradable contracts, interfaces)

📜 License
MIT — Use it, modify it, build cool stuff.

