# TokenMinter: Smart Contract for Minting and Burning Tokens

##Description
This Solidity contract, named MyToken, defines a simple token system on the Ethereum blockchain. It includes three public variables: TokenName, TokenAbbrv, and TotalSupply to store the token's name, abbreviation, and total supply, respectively. The contract uses a mapping to keep track of the token balances of different addresses. It provides two main functions: mint and burn. The mint function increases the total supply and the balance of a specified address by a given amount, effectively creating new tokens. Conversely, the burn function decreases the total supply and the balance of a specified address by a given amount, but only if the address has a sufficient balance, effectively destroying tokens. This ensures that tokens cannot be burned from an address with an insufficient balance.

### Executing program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.
Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file:

contract MyToken
{
    // public variables here
    string public TokenName = "solidity";
    string public TokenAbbrv ="developer";
    uint public TotalSupply = 0;

    // mapping variable here
    mapping (address => uint) public balance;

    // mint function
    function mint(address _address , uint _Value) public
    {
      TotalSupply += _Value;
      balance[_address] += _Value;
    }

    // burn function
     function burn(address _address , uint _Value) public
    {
      if(balance[_address] >= _Value)
      {
         TotalSupply -= _Value;
      balance[_address] -= _Value;
      }      
    }
}

## Authors
@Jagjit Singh

## License
This project is licensed under the MIT License - see the LICENSE.md file for details

