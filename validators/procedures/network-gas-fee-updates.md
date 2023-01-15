# Network Gas Fee Updates Procedure

## Gas Fee DECREASE
When updating gas fees to **LOWER** prices, the gas fee changes need to be rolled out across the network in this order:
- Validators must update their `minimum-gas-prices` values in their `app.toml` and restart their `terrad` services.
- Once validators have confirmed they have updated their `app.toml`s, clients (Terra Station, Rebel Station, etc) are free to update their gas fees accordingly.

## Gas Fee INCREASE
When updating gas fees to HIGHER prices, the gas fee changes need to be rolled out across the network in this order:
- Clients (Terra Station, Rebel Station, etc) must update their gas fees.
- Once clients have confirmed they have updated their gas fees, validators are free to update the `minimum-gas-prices` values in their `app.toml` and restart their `terrad` services to roll out the gas fee changes across the entire network.

## Additional Notes
- For any client side applications updates, the end user will also need to restart the application to be sure the gas fee changes have been properly updated on the client side application, as gas prices tend to be cached; which could result in estimation issues when the backend has been updated but the client hasn't picked up those changes from the backend yet (which restart the application would resolve).
