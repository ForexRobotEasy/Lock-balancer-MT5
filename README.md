# Lock balancer MT5

This code is an example of a lock balancer for MetaTrader 5 (MT5) platform. It is a custom indicator that is designed to manage locking and stop loss orders for a trading position.

## Input parameters

The code allows the user to define the following input parameters:

1. `LockLine` - Initial locking line for the pending order.
2. `StopLoss` - Stop loss value for the position.

## Global variables

The code uses the following global variable:

1. `lockOrderTicket` - Ticket of the lock order.

## Custom indicator initialization function - OnInit()

This function is called when the indicator is initialized. It sets the initial locking line as a pending order using the `OrderSend()` function. The function returns `INIT_SUCCEEDED` to indicate successful initialization.

## Custom indicator deinitialization function - OnDeinit(const int reason)

This function is called when the indicator is deinitialized. It checks if the lock order exists and closes it using the `OrderClose()` function. The `lockOrderTicket` variable is then reset.

## Custom indicator iteration function - OnTick()

This function is called on each tick. It checks if the lock order is still open and if the price has moved against the trader. If the conditions are met, it closes the lock order and opens a counter order as a stop loss using the `OrderClose()` and `OrderSend()` functions.

If the lock order is not open, it checks if the price has moved in favor of the trader. If this condition is met, it closes the stop loss order using the `OrderClose()` function.

## Product Description

Lock balancer MT5 is a powerful forex software designed to manage locking and stop loss orders for trading positions. It automatically handles locking and stop loss operations based on predefined input parameters.

Key Features:
- Automatically sets a locking line as a pending order.
- Monitors price movements and closes the lock order if the price moves against the trader.
- Opens a counter order as a stop loss to limit potential losses.
- Closes the stop loss order and unlocks the position if the price moves in favor of the trader.

This product is developed by Forex Robot Easy Team and is available on their website [forexroboteasy.com](https://forexroboteasy.com). Please note that ForexRobotEasy is not the official developer of this product. This code is provided as a sample that can work as described in the product. To find the official developer of this product, please refer to MQL5. 

For detailed reviews and trading results of this product, please visit [forexroboteasy.com/forex-robot-review/lock-balancer-mt5-a-review-of-this-powerful-forex-software/](https://forexroboteasy.com/forex-robot-review/lock-balancer-mt5-a-review-of-this-powerful-forex-software/).
