# Forex VPS Malaysia: Is RM37.9 a Month Real, How Many MT5 Terminals Do You Need, and What Evoxt Charges in USD (Full Plan Table)

Malaysian forex VPS plans are advertised from RM36 to RM38.90 a month, and every one of those headline figures I checked is a long-cycle prepayment price quoted before the 8% service tax. If you run one or two MT4/MT5 terminals with an EA attached, the 2 GB tier is the one you want, and the honest monthly cost lands somewhere above the sticker.

This page covers what the RM entry band actually includes, how many terminals a given amount of RAM really carries, where Evoxt's USD-priced Windows plans sit against the local hosts, and the latency question the local marketing pages tend to skip.

> **Quick pick:** Evoxt VM-1 (1 vCPU, 2 GB RAM, 20 GB storage) at $5.99/month is the smallest Windows box worth installing MT5 on. One terminal, one or two EAs, no backtesting on the live box. 👉 [Deploy the 2 GB Windows plan](https://bit.ly/EvoXt)

## Evoxt's Windows plans, all of them

Evoxt sells Windows RDP on the same VM sizes it uses elsewhere, priced in US dollars and billed monthly. The full lineup as published on its Windows RDP plan page:

| Plan | vCPU | RAM | Storage | Price (USD/mo) | Deploy |
| --- | --- | --- | --- | --- | --- |
| VM-0.5 | 1 | 512 MB | 5 GB | $2.99 | [Deploy VM-0.5](https://bit.ly/EvoXt) |
| VM-0.75 | 1 | 1 GB | 10 GB | $4.99 | [Deploy VM-0.75](https://bit.ly/EvoXt) |
| VM-1 | 1 | 2 GB | 20 GB | $5.99 | [Deploy VM-1](https://bit.ly/EvoXt) |
| VM-2 | 2 | 4 GB | 30 GB | $11.99 | [Deploy VM-2](https://bit.ly/EvoXt) |
| VM-4 | 4 | 8 GB | 60 GB | $23.99 | [Deploy VM-4](https://bit.ly/EvoXt) |
| VM-6 | 8 | 8 GB | 60 GB | $29.99 | [Deploy VM-6](https://bit.ly/EvoXt) |
| VM-8 | 8 | 16 GB | 80 GB | $47.99 | [Deploy VM-8](https://bit.ly/EvoXt) |

Prices and specs are as listed on that page and are billed in USD, so your card issuer sets the ringgit figure and adds whatever FX spread it charges. Confirm the checkout total before you pay, because plan pages rarely show add-ons or regional adjustments.

Every VM on the plan includes a weekly offsite backup at no extra cost, plus a control panel with firewall rules, VNC console access, IP reassignment and cloning. Those matter more than they sound: the firewall lets you shut every port except RDP without logging into Windows, and the firewall sits in front of the VM rather than inside it.

## What the RM36 to RM38.90 headline actually buys

Three things get folded into that number, and none of them are on the card.

**The price is a three-year prepayment.** On VPSMalaysia's Standard plan, the RM37.9 "Get Started" button points at a triennial billing cycle and carries a "Save 17%" badge. Month-to-month pricing isn't published on the page. If that 17% is measured against monthly billing, the same box costs roughly RM45.70 a month on a rolling contract. Awanprime's RM36 entry plan and Shinjiru's advertised entry rate follow the same pattern of a low sticker price attached to a long commitment.

**Service tax is excluded.** VPSMalaysia's page states it plainly: "Exclusive of 8% Service Tax." RM37.90 becomes RM40.93 once tax is added. Budget for that before comparing it to a USD invoice, which may or may not have tax applied depending on where the vendor is registered.

**The spec is the market consensus, not a bargain.** All the local entry plans converge on roughly 2 vCPU, 2 GB RAM, 50 GB NVMe, one dedicated IP, Windows Server and RDP access. You are not getting a deal at RM37.9; you are getting the standard floor.

## "Unlimited MT4/MT5" is a RAM statement wearing a marketing hat

VPSMalaysia's own FAQ gives the real number: "you can run around 6 MetaTraders on 1 GB of RAM without running a backtest." That is the vendor admitting the limit is memory, not licensing. Casbay says the same thing in different words: terminal count depends on free RAM and vCPU, and you get over-usage alerts when you push past it.

So what does that mean for a 2 GB box? Windows Server takes its share before MetaTrader loads a single chart. Deduct that and you are looking at four to six bare terminals, fewer once each one carries a stack of indicators or a heavy EA. Backtesting changes the arithmetic entirely: the strategy tester will consume everything you give it, and an optimisation run on the same box as your live terminal is how people miss entries.

Plan your RAM around terminals plus headroom, not around the word "unlimited."

## Picking a plan by terminal count

For Windows plus MT5, the two cheapest Evoxt plans are not trading machines. 512 MB and 1 GB will boot Windows, but the desktop will be sluggish and MT5 will be fighting the OS for memory. Treat VM-0.5 and VM-0.75 as Linux boxes or throwaway test environments.

- **One terminal, one account, one or two EAs, no backtesting:** VM-1 at $5.99. 20 GB of storage fits Windows, MT5 and a couple of installs. Tick history and long backtests will fill it, so prune or archive.
- **Three to six terminals across brokers or strategies:** VM-2 at $11.99. The 4 GB gives Windows room and leaves enough for several MT5 instances plus chart-heavy templates.
- **Backtesting and optimisation alongside live trading:** VM-4 at $23.99 for 8 GB. If you optimise often, keep the testing on a separate VM from the one holding open positions.
- **Running other people's accounts or a small prop setup:** VM-6 gives you eight cores on the same 8 GB, which helps when several MT5 instances are compiling or backtesting at once. VM-8 at 16 GB is for people who already know they need it.

Most readers running a single EA will never use anything above VM-1, and paying for VM-2 "just in case" is $72 a year for capacity you aren't touching. 👉 [Start with the 2 GB plan and scale later](https://bit.ly/EvoXt)

## Where Evoxt fits, and what you give up

Evoxt runs a Malaysia location alongside its other regions, and that location peers locally at MyIX, the Malaysian internet exchange. For a trader in KL or Penang, that means the remote desktop feels like a local machine.

What you give up compared with the RM-priced local hosts is mostly convenience. There is no pre-installed MT4 or MT5; you install the terminal yourself, which takes ten minutes and one download. Storage is tighter: 20 GB on VM-1 against the 50 GB NVMe that local entry plans include, and 30 GB on VM-2 against 60 GB. Neither is a problem for a trading box unless you hoard tick data.

What you get in return is a lower entry point and monthly billing in USD instead of a multi-year ringgit commitment. Evoxt's own FAQ documents upgrades, and the plan ladder moves in clean steps (2 GB, 4 GB, 8 GB), so growing means rebooting into the next size rather than renegotiating a contract.

One caveat worth knowing before you pay: reviewers have flagged Evoxt's policy on non-refundable account credits as something that caught them out. If you might change your mind, ask support how a cancellation is handled before you top up a balance, rather than after.

## The latency question: which hop are you paying for?

Local providers advertise latency "as low as 2ms" to your broker. That claim only holds if your broker's servers are in the same city as the VPS.

Two different hops are involved. The first is your home connection to the VPS, which decides how smooth the remote desktop feels. The second is the VPS to your broker's trade server, which decides how fast your orders arrive. A Kuala Lumpur VPS fixes the first hop beautifully for a Malaysian trader. It does nothing for the second if your broker's MT4 server sits in London, New York or Tokyo, because those orders still travel the same distance they would from your house.

You can find out where your broker's server lives: the MT4 or MT5 login dialog shows the server name, and most brokers publish the data centre location. If it's London, a VPS in London will beat a VPS in KL on execution, and your RDP session will just be a bit laggier. If your broker is in Singapore or Kuala Lumpur, the Malaysia node is the right call. 👉 [Check Evoxt's Malaysia region before you commit](https://bit.ly/EvoXt)

## How the local hosts compare

All figures below are as published on each provider's own pages. None of them include a link, because you can find them yourself.

| Provider | Entry price | Entry spec | Locations | Notes |
| --- | --- | --- | --- | --- |
| VPSMalaysia | RM37.9/mo on a 3-year cycle, excl. 8% tax | 2 vCPU / 2 GB / 50 GB NVMe / 1 IP | Malaysia (MY03), New York, Amsterdam | Windows Server 2012–2022, pre-installed MT4/5, 30-day money-back with conditions |
| Awanprime | RM36/mo | 2 vCPU / 2 GB / 1 IP | Malaysian data centre | 99.9% uptime SLA, Windows plus RDP, no setup fee, local support team |
| Evoxt | $5.99/mo for the 2 GB plan | 1 vCPU / 2 GB / 20 GB | Malaysia among its regions | Windows RDP plans, weekly offsite backup included, USD billing |

Casbay is the other name that comes up, and its Cyberjaya Tier III facility is a genuine local selling point: it supports multiple MT5 terminals through separate install paths and charges no setup fee. The prices published on its site date from earlier years, though, so treat any ringgit figure you find there as unverified until you ask for a current quote.

If pre-installed MT4/5, a Malaysian support desk and RM billing matter more to you than price, VPSMalaysia and Awanprime are both reasonable. If you want to pay monthly, in dollars, and don't mind installing the terminal yourself, Evoxt is cheaper at the same RAM.

## Questions that come up before ordering

**Can I connect from my phone?** Yes. Microsoft Remote Desktop is free on iOS and Android, and any RDP client works. You get an IP address, a username and a password, and you're on the same desktop you left.

**Is 20 GB of storage enough?** For Windows, MT5 and two or three terminal installs, yes. Historical tick data and repeated backtests will eat it quickly. If you download years of M1 data, take VM-2 for the 30 GB.

**Do I need to buy a Windows licence separately?** No. The plans on Evoxt's Windows RDP page come with Windows included.

**What if I outgrow the plan?** Evoxt documents upgrades in its FAQ, and the tiers step up in clean increments. Confirm the process with support if you expect to move within the first month.

**Is there a free backup?** Yes. Every VM gets a weekly offsite backup at no cost. Leave it switched on.

## Before you order, check two things

First, the billing currency and period. Evoxt bills in USD monthly, so your statement will show a converted amount plus whatever your bank charges for the conversion. Local hosts bill in ringgit, usually on a cycle you have to choose at checkout, and the cheapest displayed rate is generally the longest commitment.

Second, where your broker's trade server sits. A Malaysian VPS is the right answer for a Malaysian or Singaporean broker and the wrong answer for one in London. Get that fact first, then pick the region, then pick the size.

For a single MT5 terminal with one EA, VM-1 at $5.99 handles it. For four to six terminals across brokers, VM-2 at $11.99 is the sane step up, and anything above that should be justified by backtesting or by accounts you're managing for other people.

👉 [Deploy Evoxt's 2 GB Windows plan](https://bit.ly/EvoXt)
