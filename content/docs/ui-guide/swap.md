---
weight: 20
title: Swap
---

## Swap Main

![main](/docs/ui-guide/swap_main.png)

1. Brief chart (To be added) - You may check the brief chart of the selected pairs.
1. Trade type selection (To be added) - You may choose the trading type between instant swap & limit order. (Only instant swap is available for now)
1. Swap setting - You may configure some options of the swap trading.
1. Token selection - You may choose two assets from the lists.
1. Address copy button - Once you selected a token, you may copy the address of the token, and can compare it to the address from the disclosure application.
1. Swap direction flip button - If you don't want to change assets but only change the swap direction, you may click this button.

## Token Selection

![token selection](/docs/ui-guide/token_selection.png)

You may select the token you want to swap. If you click the star of the each asset, the asset is marked as the favorite, and it appears on the **Bookmark** tab.

## Setting

![Setting](/docs/ui-guide/swap_setting.png)

1. Slippage tolerance - When you select asset pair and input how much you want to swap, Dezswap simulates the result and shows the expected amount. But the number can vary by the timing between you simulated and the unexpected swap transaction executed. If you set the number of it, your swap transaction raises failure if the actual result is different from the simulated result. The number is your allowance of the difference(may be loss).
1. Transaction deadlines - If the chain network is too busy to process, your transaction would not be executed and could be remain on the memory queue. But if it remains long time, the swap rate could be different and it could cause your loss. If you set this parameter, your swap transaction will only be valid within the given time range and will raise an error when your transaction is executed after the given lifetime.
1. Auto router (To be done) - If there is no direct pair between two assets, Dezswap helps finding the best path from the all possible multihop swaps.
