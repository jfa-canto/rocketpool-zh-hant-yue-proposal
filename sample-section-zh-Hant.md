> **Sample section. Draft for the GMC application, not yet independently reviewed.**
> Checked against: `rocket-pool/docs.rocketpool.net` @ `main`, 27 Oct 2026 (`docs/en/liquid-staking/overview.mdx`, `via-rp.mdx`, `via-l2.mdx`, `protocol/faq.mdx`).
> Disclosure: drafted with an AI writing assistant; edited by a human; all protocol facts link to the official English docs.

# 第 1 節　rETH 是什麼？為什麼它的「匯率」會慢慢上升？

## 一句話版本

**rETH 是你把 ETH 存入 Rocket Pool 之後拿到的代幣。你手上 rETH 的「數量」不會變，但每 1 枚 rETH 可以換回的 ETH 會隨着質押獎勵累積而慢慢增加。**（來源：[Staking Overview › The rETH Token](https://docs.rocketpool.net/en/liquid-staking/overview#the-reth-token)）

## 1.1　你的 ETH 去了哪裏？

以太坊的驗證者（validator）需要 32 ETH 作為抵押。在 Rocket Pool，**節點營運者（node operator）自己出 4 ETH 保證金**，其餘 **28 ETH 來自質押池**，也就是像你這樣的 rETH 持有人存入的 ETH。兩者合起來，組成一個「megapool 驗證者」。
（來源：[How Rocket Pool Works](https://docs.rocketpool.net/en/liquid-staking/overview#how-rocket-pool-works)）

驗證者會從三個地方賺取獎勵：

1. 信標鏈（Beacon Chain）的共識獎勵
2. 出塊時的交易優先費（priority fees）
3. MEV 獎勵

這些獎勵的一部分會反映在 rETH 的價值上。

## 1.2　「數量不變、價值上升」是什麼意思？

很多代幣用「發新幣」（rebase）的方式派發收益，你錢包裏的數字會每天增加。**rETH 不是這樣。** 它的做法是讓 **rETH 對 ETH 的兌換率** 上升：

| 時間 | 你持有的 rETH | 1 rETH 可換回 | 你的 rETH 約值 |
|---|---|---|---|
| 存入當日（假設 1 : 1） | 10 rETH | 1.00 ETH | 10 ETH |
| 數年後（官方文件的例子） | 10 rETH | 1.25 ETH | 12.5 ETH |

> 上表數字取自官方文件的教學例子，**不是收益預測**。實際兌換率請在 [stake.rocketpool.net](https://stake.rocketpool.net/) 查看。

官方文件指出，兌換率大約 **每 24 小時** 根據節點的信標鏈獎勵更新一次。

**台灣讀者的小提醒：** 因為 rETH 的數量不變，有些司法管轄區只在「換入」或「換出」時才可能產生課稅事件。不同地區規定不同，**本指南不構成稅務意見**，請自行查證或諮詢專業人士。（來源：[Tax Implications](https://docs.rocketpool.net/en/liquid-staking/overview#tax-implications)）

## 1.3　匯率一定只升不降嗎？

**通常會上升，但並非保證。** 官方 FAQ 說明了虧損時的處理順序：

1. 如果某個節點表現差而導致 ETH 損失，**先由該節點營運者的保證金（以及其 RPL）賠償**；
2. 如果仍不足夠，餘下的損失會 **攤分到整個網絡**，表現為 rETH 相對價值的下降。

（來源：[FAQ › How does the protocol protect the value of rETH?](https://docs.rocketpool.net/en/protocol/faq#how-does-the-protocol-protect-the-value-of-reth)）

此外還有其他風險，第 2 節會逐一說明：

- **智能合約風險**：合約已開源並經審計，但審計不等於零風險。
- **流動性風險**：直接向協議贖回 ETH，需要質押池中有足夠的 ETH。不足時，網站會改用 CoW Swap 等第三方路徑，可能有滑價。
- **二級市場價格**：在 DEX 上，rETH 的成交價可能短暫偏離官方兌換率。

## 1.4　我需要多少 ETH？

最低 **0.01 ETH** 即可存入。經協議路徑存入會收取 **0.05% 存入手續費**，另加以太坊網絡的 gas 費。金額較小時，gas 可能比手續費更貴，第 3 節會比較各種取得方法。
（來源：[FAQ › minimum deposit](https://docs.rocketpool.net/en/protocol/faq#what-is-the-minimum-deposit)、[Staking via Rocket Pool › Protocol Route](https://docs.rocketpool.net/en/liquid-staking/via-rp)）

## 1.5　認清「真」的 rETH

騙徒常發行同名的假 rETH。請只認以下官方合約地址（來源：官方文件；請在區塊瀏覽器再次核對）：

| 網絡 | rETH 合約地址 |
|---|---|
| Ethereum 主網 | `0xae78736Cd615f374D3085123A210448E74Fc6393` |
| Arbitrum | `0xec70dcb4a1efa46b8f2d97c310c9c4790ba5ffa8` |
| Optimism | `0x9bcef72be871e61ed4fbbc7630889bee758eb81d` |
| Hoodi 測試網（練習用） | `0x7322c24752f79c05ffd1e2a6fcb97020c1c264f1` |

> **永遠不要** 把主網的真 ETH 轉到測試網。測試網只用免費的測試幣。

---

### 🇭🇰 廣東話速讀版（書面粵語）

> **rETH 係咩？** 你將 ETH 放入 Rocket Pool，佢就會俾返你 rETH。你手上嘅 rETH 粒數唔會變，但係每粒 rETH 可以換返嘅 ETH 會慢慢多咗，因為啲質押獎勵會累積落去個兌換率度。
>
> **穩唔穩陣？** 通常個兌換率係向上，但唔係保證。如果有節點蝕錢，會先由個節點營運者自己嘅保證金頂住；唔夠先至會攤分俾全網，令 rETH 價值跌少少。另外仲有智能合約風險，同埋贖回嗰陣可能唔夠流動性。
>
> **最少要幾多？** 0.01 ETH 就玩得。走官方路徑會收 0.05% 手續費，再加 gas。
>
> **小心假幣！** 只認官方合約地址（睇上面個表）。有人 DM 你話「送 rETH 空投」，十居其九係呃人。
>
> *（廣東話部分由母語為粵語的作者撰寫及審閱。）*

---

### 本節詞彙（節錄自 glossary.csv）

質押（staking）・驗證者（validator）・節點營運者（node operator）・保證金（bond）・質押池（deposit pool）・兌換率（exchange rate）・滑價（slippage）・智能合約（HK）／智慧合約（TW）・網絡（HK）／網路（TW）
