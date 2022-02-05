1. Test train Split
from sklearn.model_selection import train_test_split
X_train, X_test, y_train, y_test = train_test_split(df['feature'],df['Class'] , test_size=0.33, random_state=42)
1. K Fold Cross validation
2. Cros val score
3. Cros val pred