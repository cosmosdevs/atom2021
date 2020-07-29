# Peggy

## Question

Should Peggy be deployed as a Shared Security Zone or module in Gaia as part of the Cosmos SDK?

## Context

In April 2020, Althea proposed an [DeFi enabled Ethereum bridge for Cosmos](https://blog.althea.net/defi-enabled-ethereum-bridge-for-cosmos/) for a DEFI enable PegZone.

The Interchain Foundation has provided [Althea](https://blog.althea.net/solid-foundations-for-peggy/)with resources to implement the technical components of this vision.

Althea is developing a Cosmos SDK [module](https://github.com/cosmos/peggy/tree/althea-peggy)+ solidity contracts here.

A Schelling point has not been established on how this module should be deployed.

### Option 1

 ATOM/(or another token:Althea?) holder set establishes a new blockchain purpose built for Peg zone management.  Via an on chain script powered by COSM-WASM, the Cosmos Hub adds the ability for validators to opt their ATOMs into faults on the Peggy chain and a COSM WASM contract is added that recognizes Peggy specific faults and slashes ATOMs. An additional property would all the victims to be reimbursed via slashed or inflated ATOMs from the Hub.

### Option 2

Deploy Peggy as module in Gaia as the Hub. Hub Validators ( maybe some day delegators) vote in the Liquidity DAO managing the collateral. ERC20 tokens are minted by the Hub onto the Cosmos Network. Interests rate/ earnings  would be distributed to staked ATOM holders.

## The case for Option 1: Sovereign Chains with Shared Security

In Option 1, the Cosmos Hub specializes as the security/ accountability layer of Cosmos. ATOM holders are not directly responsible for managing the Peg, the Ethereum event and instead a subset of validators opt into participation and governance of Peggy chain.

Because of the separation of concerns between Peggy and the Cosmos Hub the Cosmos hub can credibly and independently respond to collusion and malfeasance by the operators of Peggy.

The Cosmos Hub can offer this service to multiple similar Pegs rather than nominating a single blessed Peg zones.

The Cosmos hub will be required to be able to analyze pairs of state transitions and smart contract executions on the Cosmos Hub for correctness. This will involve being able execute module logic and block headers and ethereal smart contract state. The most likely implementation target for these capabilities is Rust  executed inside CosmWasm.

The Smart Contract can be made more efficient by a smaller number of signers.

## The case for Option 2: Integrating Peggy into the Cosmos Hub

Integrate Peggy directly into Gaia. Atom holder would directly earn yield on pegged assets and validators would be operating the Ethereum network oracle.  The Validators would need to sign transactions on the Ethereum chain and participate in the governance of pegged assets connected to DEFI.

They would also facilitate accounting for and tracking of yield earned on Ethereum back to ATOM holders for managing the Peg.

Ultimately the security of this system will depend on incentive alignments and honesty and accountability assumptions. There is no natural place to holder Cosmos Hub validators accountable and they are unlikely to punish themselves if 2/3rds fault or the software goes wrong.

I’d advocate for some mechanism for ATOM holders to provide ATOMs to anyone who loses funds due a fault in the Peg.
