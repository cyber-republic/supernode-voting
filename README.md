# Voter Reward Payout Script for DPOS Nodes

## Public Supernode Overview
The public supernode overview is the public facing collection of statistics about the supernode, its voters and payout details anyone can see in their browser.
- Supernode unique short description & links (optional)
- Date of last payout
- Date of next payout
- Rank of supernode
- Productivity (uptime since eligibility to forge rewards)
- Approval (percentage of votes across entire network)
- Total payout until now
- Total pending payout (since last payout)
- Number of voters
- List of voters by address -> sorted in descending order by vote weight
- Language switcher (localization)

## Supernode Payout Options
The supernode payout options can be set by the supernode in the configuration. These settings are protected and are only available to the supernode.
- Calculate own costs ( monthly costs in USD -> convert USD to amount of Rewards)
- Total percentage of rewards to distribute from profit (income minus costs) OR total
- Distribution schedule: weekly, monthly, custom, manual
- Minimum payout amount
- Minimum voter weight to be eligible for payout
- Subtract transaction fee from voter payout (yes/no)
- Coins to release: ELA + (later from sidechains) checkbox
- Blacklist address from payout (for example if key is lost by voter)

**Required Voter Details:**
- Voter public address
- Voter DID
- Initial vote or Change of vote (initial vote, and for every change of votes: repeat + log)
  - Start date of vote + vote weight for node
  - End date of vote -> set vote weight to null

## Supernode Payout Process
The payout process is the distribution of funds based on the previously collected statistics about voters.
### Manual Payout Option (Most secure)
  - Download list of voter statistics into a csv / xml / json format
  - Open wallet
  - Load list
  - Double check list (full overview)
  - Submit transactions -> payout
  - Optional: Statistics Script running on server may recognize payouts or can be marked manually
  - Requirements: Allow downloads of statistics from script, Web Wallet integration for uploads and starting bulk transactions OR custom desktop wallet for supernodes

### Automated Payout option
- Script gathers voter statistics automatically
- Payouts are initiated based on cron jobs (scheduled)
- Requirements: Wallet API integration -> very high security standards needed
