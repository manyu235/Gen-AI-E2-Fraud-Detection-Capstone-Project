"""
Generate realistic banking fraud detection dataset
"""
import json
import random
from datetime import datetime, timedelta

# Seed for reproducibility
random.seed(42)

# Banking merchants with categories and typical amounts (name, category, min, max, fraud_probability)
merchants_data = [
    # Retail - Normal transactions (low fraud rate)
    ('Walmart', 'retail', 50, 200, 0.02),
    ('Target', 'retail', 40, 180, 0.02),
    ('Costco', 'retail', 100, 300, 0.03),
    ('Amazon', 'retail', 20, 150, 0.01),
    ('Best Buy', 'retail', 200, 1500, 0.05),
    ('Apple Store', 'retail', 500, 3000, 0.08),
    ('Home Depot', 'retail', 80, 500, 0.03),
    ('CVS Pharmacy', 'retail', 15, 80, 0.01),
    
    # Gas stations
    ('Shell Gas', 'retail', 30, 80, 0.01),
    ('Chevron', 'retail', 25, 75, 0.01),
    ('Exxon', 'retail', 28, 70, 0.01),
    
    # Restaurants
    ('Starbucks', 'retail', 5, 20, 0.01),
    ('McDonalds', 'retail', 8, 30, 0.01),
    ('Local Restaurant', 'retail', 25, 100, 0.02),
    ('Fine Dining', 'retail', 80, 250, 0.05),
    ('Pizza Hut', 'retail', 15, 50, 0.01),
    
    # Groceries
    ('Whole Foods', 'retail', 60, 200, 0.02),
    ('Trader Joes', 'retail', 40, 120, 0.02),
    ('Safeway', 'retail', 50, 150, 0.02),
    
    # Utilities & Bills (very low fraud)
    ('Electric Company', 'bill_payment', 80, 200, 0.01),
    ('Water Utility', 'bill_payment', 40, 100, 0.01),
    ('Internet Provider', 'bill_payment', 50, 150, 0.01),
    ('Phone Bill', 'bill_payment', 60, 120, 0.01),
    ('Gas Company', 'bill_payment', 70, 180, 0.01),
    
    # Banking services
    ('ATM Withdrawal', 'atm', 20, 500, 0.03),
    ('Mobile Deposit', 'check', 200, 2000, 0.02),
    ('Bank Transfer', 'p2p', 50, 1000, 0.05),
    
    # P2P payments
    ('Venmo', 'p2p', 20, 500, 0.08),
    ('PayPal', 'p2p', 30, 800, 0.08),
    ('Zelle', 'p2p', 50, 1000, 0.10),
    
    # High-risk merchants (HIGH fraud rate)
    ('Las Vegas Casino', 'gambling', 100, 5000, 0.40),
    ('Online Poker Site', 'gambling', 50, 3000, 0.45),
    ('Sports Betting', 'gambling', 100, 2000, 0.35),
    ('Atlantic City Casino', 'gambling', 200, 4000, 0.38),
    
    ('International Wire Service', 'wire_transfer', 1000, 20000, 0.50),
    ('Offshore Bank Transfer', 'wire_transfer', 5000, 25000, 0.60),
    ('Western Union', 'wire_transfer', 500, 10000, 0.45),
    
    ('Coinbase', 'crypto', 500, 15000, 0.55),
    ('Crypto.com', 'crypto', 300, 12000, 0.50),
    ('Bitcoin ATM', 'crypto', 200, 10000, 0.50),
    ('Binance', 'crypto', 400, 18000, 0.52),
    
    ('Quick Cash Advance', 'cash_advance', 300, 5000, 0.45),
    ('Payday Loan Center', 'cash_advance', 500, 3000, 0.40),
    ('Express Cash', 'cash_advance', 400, 4000, 0.42),
    
    ('Check Cashing Store', 'check', 200, 5000, 0.35),
    ('Pawn Shop', 'cash_advance', 100, 2000, 0.30),
    
    ('Gift Card Superstore', 'retail', 100, 5000, 0.40),
    ('Prepaid Card Center', 'retail', 200, 3000, 0.35),
    ('Money Order Service', 'wire_transfer', 300, 8000, 0.38),
]

locations = [
    'New York', 'Los Angeles', 'Chicago', 'Houston', 'Phoenix',
    'Philadelphia', 'San Antonio', 'San Diego', 'Dallas', 'San Jose',
    'Austin', 'Jacksonville', 'Seattle', 'Denver', 'Boston',
    'Online', 'International', 'Las Vegas', 'Miami', 'Atlanta'
]

# Generate users
num_users = 50
users = [f'user_{i:03d}' for i in range(1, num_users + 1)]

# User spending patterns
user_avg_spending = {user: random.uniform(100, 500) for user in users}

print("Generating banking transactions dataset...")

transactions = []
base_date = datetime.now() - timedelta(days=90)  # Last 90 days

for txn_id in range(1, 5001):  # 5000 transactions
    # Select merchant
    merchant, category, min_amt, max_amt, fraud_prob = random.choice(merchants_data)
    
    # Determine if fraud
    is_fraud = random.random() < fraud_prob
    
    # Select user
    user = random.choice(users)
    
    # Generate amount
    if is_fraud:
        # Fraud: unusual amounts
        if random.random() < 0.5:
            amount = random.uniform(max_amt * 0.8, max_amt * 3)  # Large amount
        else:
            amount = random.uniform(min_amt, max_amt)
    else:
        # Normal: typical amounts
        amount = random.uniform(min_amt, max_amt)
        # Sometimes normal large purchases
        if random.random() < 0.05:
            amount = random.uniform(max_amt, max_amt * 2)
    
    amount = round(amount, 2)
    
    # Generate timestamp
    days_offset = random.randint(0, 89)
    
    if is_fraud:
        # Fraud: more likely at night
        hour_weights = [3]*6 + [1]*12 + [2]*6  # Night heavy
        hour = random.choices(range(24), weights=hour_weights)[0]
    else:
        # Normal: mostly during day
        hour_weights = [1]*6 + [5]*12 + [2]*6  # Day heavy
        hour = random.choices(range(24), weights=hour_weights)[0]
    
    minute = random.randint(0, 59)
    second = random.randint(0, 59)
    timestamp = base_date + timedelta(days=days_offset, hours=hour, minutes=minute, seconds=second)
    
    # Location
    if is_fraud and random.random() < 0.3:
        location = 'International'  # More international fraud
    elif category in ['gambling']:
        location = random.choice(['Las Vegas', 'Atlantic City', 'Online'])
    else:
        location = random.choice(locations)
    
    # Card present
    if category in ['atm'] or (category == 'retail' and location not in ['Online', 'International']):
        card_present = random.random() < 0.7
    else:
        card_present = False
    
    # Description
    descriptions = {
        'retail': f'Purchase at {merchant}',
        'gambling': f'Gambling transaction at {merchant}',
        'wire_transfer': f'Wire transfer via {merchant}',
        'crypto': f'Cryptocurrency purchase at {merchant}',
        'cash_advance': f'Cash advance from {merchant}',
        'check': f'Check transaction at {merchant}',
        'bill_payment': f'Bill payment to {merchant}',
        'atm': f'ATM withdrawal at {merchant}',
        'p2p': f'P2P payment via {merchant}',
    }
    
    transaction = {
        'transaction_id': f'TXN{txn_id:05d}',
        'user_id': user,
        'amount': amount,
        'merchant': merchant,
        'merchant_category': category,
        'description': descriptions.get(category, f'Transaction at {merchant}'),
        'timestamp': timestamp.isoformat(),
        'location': location,
        'card_present': card_present,
        'is_fraud': is_fraud  # Ground truth label
    }
    
    transactions.append(transaction)

# Sort by timestamp
transactions.sort(key=lambda x: x['timestamp'])

# Save to JSON
print("Saving dataset...")
with open('data/banking_transactions.json', 'w') as f:
    json.dump(transactions, f, indent=2)

# Create statistics
total = len(transactions)
fraud_count = sum(1 for t in transactions if t['is_fraud'])
legitimate_count = total - fraud_count

# Category breakdown
categories = {}
fraud_by_category = {}
for t in transactions:
    cat = t['merchant_category']
    categories[cat] = categories.get(cat, 0) + 1
    if t['is_fraud']:
        fraud_by_category[cat] = fraud_by_category.get(cat, 0) + 1

print("\n" + "="*70)
print("✅ DATASET GENERATION COMPLETE")
print("="*70)
print(f"\n📊 Total Transactions: {total:,}")
print(f"   • Legitimate: {legitimate_count:,} ({legitimate_count/total:.1%})")
print(f"   • Fraudulent: {fraud_count:,} ({fraud_count/total:.1%})")

print(f"\n📈 Transactions by Category:")
for cat, count in sorted(categories.items(), key=lambda x: x[1], reverse=True):
    fraud_in_cat = fraud_by_category.get(cat, 0)
    print(f"   • {cat:20s}: {count:4d} ({fraud_in_cat} fraud, {fraud_in_cat/count:.1%})")

print(f"\n💾 Saved to: data/banking_transactions.json")
print("="*70 + "\n")
