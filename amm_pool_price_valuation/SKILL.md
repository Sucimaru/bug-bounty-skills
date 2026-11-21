# AMM Pool Price Valuation

## Identify the pair and both tokens

- Read `token0()` and `token1()` from the pair contract before you read any reserve.

- Record which reserve belongs to which token and name the quote token you will price against.

- Read `decimals()` on chain for both tokens and record both numbers beside the pair address and the block number.

- Never assume a decimal count from the token symbol or from the same token on another chain.

## Convert reserves before you divide

- Read `getReserves()` from the pair contract and keep the raw values untouched in your notes.

- Divide each raw reserve by ten raised to the power of that token decimal count to get its converted reserve.

- Calculate the token price only from the converted reserves by dividing the converted quote reserve by the converted token reserve.

- Never report a price from the raw reserve ratio and never divide a raw reserve by a converted reserve.

## Cross-check the price against executable liquidity

- Get a swap quote for the amount you value through the Binance Agentic Wallet skill and record what it returns.

- Compare the quote with the pool price and with a DexScreener price for the same pair when one exists.

- Treat the pool price as indicative only when the quote reports no liquidity or when the converted quote reserve is too small to absorb the amount.

- Stop and recheck both decimal counts when the sources disagree by a large factor instead of reporting the first price you calculated.

## Report the value and the sell decision

- Report the raw reserves, both decimal counts, both converted reserves, the price, the quote result and the block number together.

- Calculate the holding value by multiplying the holding amount by the converted price.

- Compare a sell threshold against the converted holding value only and state whether the threshold is met on that basis.

- Say plainly when the value is not sellable at the reported price because liquidity is too thin or the quote is unavailable.

## Available connectors

- Use `muse.connector_search` to find other connectors and `muse.skill_search` to find related skills.

- If nothing here fits, look on the web for a maintained API or MCP server and set it up with [Custom Connectors and MCPs](/opt/muse/skills/custom-connector-setup/SKILL.md), or build a custom connector.

## Websites

- [DexScreener](https://dexscreener.com/) for an independent pair price and liquidity view. Carry the pair address into the lookup and verify the price and liquidity match the converted reserves you calculated.

## Alternatives for better results

- Use the DexScreener price as the primary price when the pool reserves are too small to support the amount you value.

- Value a large holding in tranches when a single sale would move the pool price materially.

- Re-read the pair at a fresh block when the reserves or the quote change between your calculation and your report.
