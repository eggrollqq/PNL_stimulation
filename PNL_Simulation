import random

# Initialize simulation parameters
balance = 5000  # Starting account balance in dollars
contracts = 0.5  # Initial number of contracts to trade
contracts_maximum = 100  # Maximum allowed contracts (position cap)
balance_per_contract = 5000  # Required balance per contract (scaling factor)
win_rate = 0.60  # Probability of a winning trade (60%)
reward_points = 20  # Points gained on winning trades
risk_points = 10  # Points lost on losing trades
points_value = 50  # Dollar value per point
trade_count = 251  # Number of trades to simulate (1 year of trading days)

# Tracking variables
wins = 0  # Count of winning trades
highest_balance = balance  # Tracks the peak account value
highest_draw = 0  # Tracks the maximum drawdown percentage

def to_percent(float_value):
    """Converts a decimal value to a percentage string"""
    return f"{round(float_value * 100)}%"

# Main simulation loop
for i in range(1, trade_count + 1):
    # Determine if this trade is a win (based on win_rate)
    coinflip = random.random() < win_rate

    # Calculate potential profit/loss for this trade
    reward = contracts * reward_points * points_value
    risk = contracts * risk_points * points_value

    # Update account balance based on trade outcome
    if coinflip:
        balance += reward
        wins += 1
    else:
        balance -= risk

    # Update peak balance and drawdown statistics
    if balance > highest_balance:
        highest_balance = balance
    draw = (highest_balance - balance) / highest_balance
    if draw > highest_draw:
        highest_draw = draw

    # Print trade details
    print(f"#{i}, ${balance:,}, contracts: {contracts}, reward: {reward:,}, risk: {risk:,}, draw: {to_percent(draw)}, win: {coinflip}")

    # Adjust position size based on current balance
    contracts = balance // balance_per_contract
    # Ensure contracts stay within bounds (1 to contracts_maximum)
    contracts = max(1, min(contracts, contracts_maximum))

# Print final performance statistics
print(f"\nFinal Results:")
print(f"Ending Balance: ${balance:,}")
print(f"Projected Win Rate: {to_percent(win_rate)}")
print(f"Actual Win Rate: {to_percent(wins / trade_count)}")
print(f"Reward/Risk Ratio: {reward_points / risk_points}:1")
print(f"Maximum Drawdown: {to_percent(highest_draw)}")
