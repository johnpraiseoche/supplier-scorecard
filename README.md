# supplier-scorecard
Python tool that ranks suppliers using weighted scores

# Supplier scorecard: ranks suppliers by weighted score

suppliers = {
    "Alpha Ltd": {"price": 8, "quality": 7, "delivery": 9},
    "Beta Supplies": {"price": 6, "quality": 9, "delivery": 7},
    "Gamma Co": {"price": 9, "quality": 6, "delivery": 6},
}

weights = {"price": 0.4, "quality": 0.4, "delivery": 0.2}

def score(ratings):
    return sum(ratings[k] * weights[k] for k in weights)

ranked = sorted(suppliers.items(), key=lambda s: score(s[1]), reverse=True)

for name, ratings in ranked:
    print(f"{name}: {score(ratings):.1f}")
