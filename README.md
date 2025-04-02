# PNL_stimulation

## Trading Strategy PNL_Simulation

## Overview

This Python script simulates a trading strategy over 254 trading days (approximately one year). The simulation models a trading approach with position sizing that scales with account balance while maintaining risk management through fixed reward/risk ratios and position limits.

### Key Features

Dynamic Position Sizing: Contracts scale with account balance (1 contract per $5000)

Risk Management:

  - Fixed 2:1 reward:risk ratio (20 vs 10 points)

  - Maximum contracts capped at 100

Performance Tracking:

  - Tracks actual vs projected win rate

  - Monitors maximum drawdown

  - Shows account balance progression

### Parameters

Parameter	Default Value	Description:
  - balance	5000	Starting account balance in dollars
  - contracts	0.5	Initial number of contracts
  - contracts_maximum	100	Maximum allowed contracts
  - balance_per_contract	5000	Required balance per contract
  - win_rate	0.60	Probability of winning a trade (60%)
  - reward_points	20	Points gained on winning trades
  - risk_points	10	Points lost on losing trades
  - points_value	50	Dollar value per point
  - trade_count	254	Number of trades to simulate (1 year)
   
Output Metrics:
  - Trade-by-trade details: Shows each trade's outcome, balance, position size, and drawdown

### Final performance statistics:

Ending account balance

Projected vs actual win rate

Reward/risk ratio

Maximum drawdown experienced

### How to Use

Clone the repository or copy the script

Ensure you have Python installed (3.6+ recommended)

Run the script: python trading_simulation.py

Review the output in your terminal

### Customization

You can easily modify the simulation parameters to test different scenarios:

Change the win_rate to test different success probabilities

Adjust the reward_points and risk_points to test different risk/reward ratios

Modify balance_per_contract to change how quickly position sizes scale

Change trade_count to simulate different time periods

### Example Output

```
#1, $6,000.00, contracts: 0.5, reward: 500, risk: 250, draw: 0%, win: True
#2, $5,750.00, contracts: 1, reward: 1,000, risk: 500, draw: 4%, win: False
...
#254, $142,350.00, contracts: 28, reward: 28,000, risk: 14,000, draw: 12%, win: True

Final Results:
Ending Balance: $142,350
Projected Win Rate: 60%
Actual Win Rate: 58%
Reward/Risk Ratio: 2.0:1
Maximum Drawdown: 15%
```

License
MIT License
