# Questions

### What is the best way to handle strings in Move?

### What is the best way to handle time in Move?

Answer provided by Sam Blackshear:

> For now, we only have a coarse notion of time available via epoch numbers. A new epoch begins every 24 hours.
>
> The current epoch number can be read in Move via SuiSystem::epoch: https://github.com/MystenLabs/sui/blob/main/sui_programmability/framework/sources/Governance/SuiSystem.move#L262, but we are working on making the epoch number readable from TxContext, which will be more convenient (https://github.com/MystenLabs/sui/issues/1980).
>
> A finer-grained notion of time is coming, but will take a bit longer--follow https://github.com/MystenLabs/sui/issues/1696 for updates.

### Can you generate a random number in Move?
