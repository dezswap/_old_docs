---
weight: 20
title: Swap
---

## Swap Main

![main](/docs/ui-guide/swap_main.png)

1. Price chart - A brief price chart of the selected pairs. It contains a graph of different time units. This feature will be added soon.
1. Trade type selection - A user can choose the trading type between instant swap & limit order. (Only instant swap is available now)
1. Swap setting - options for the more sophisticated swap.
1. Token selection - a listed asset to be swapped.
1. Address copy button - The button allows users to copy the token's address to verify the exact token information.
1. Asset flip button - A user can flip assets by clicking the button.

## Token Selection

![token selection](/docs/ui-guide/token_selection.png)

Select a token to trade. Click the star on each asset to mark it as a favorite, which will appear in the **Bookmarks** tab.

## Setting

![Setting](/docs/ui-guide/swap_setting.png)

1. Slippage tolerance - Dezswap simulates the result and shows the expected amount by a pair picked and input amount. The received amount can vary from your simulation over time. The slippage tolerance prevents the actual result from being different from the simulated result. The number is a ratio of the spread and the expected amount from the result of a trade.
1. Transaction deadlines - If the chain network is too busy to process, your transaction may not be executed immediately but could be remained in the memory queue, waiting for its turn. The swap rate can be changed when it stays long, which increases the possibility of causing your loss. This parameter helps a transaction only be valid within the given time range.
1. Auto router - In case of no direct pair between two selected assets, Dezswap takes the best path from all possible multi-hop swaps. This feature will be implemented in the near future.
