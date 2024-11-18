# Ex.No: 13 Machine Learning – Mini Project - Route Optimization Model Using Ridge Regression 
### DATE: 04/11/2024       
### NAME: NANDA KISHORE R
### REGISTER NUMBER : 212222060157
### AIM: 
To write a program to train a route optimization model using Ridge Regression
###  Algorithm:
Step 1: Load the AI model using joblib.
Step 2: Check if the model has feature names to ensure input consistency.
Step 3: Create a structured input DataFrame with logistic features (traffic delay, capacities, fuel, etc.).
Step 4: Convert the input data into a pandas DataFrame for model compatibility.
Step 5: Pass the input data to the loaded model for prediction.
Step 6: The model processes the input and generates route optimization predictions.
Step 7: Display or store the predicted results for further analysis.
Step 8: Handle any errors during the prediction phase and stop the program.


### Program:
``` 
import joblib
import pandas as pd

# Load the pre-trained model
model_filename = 'route_optimization_model.pkl'
loaded_model = joblib.load(model_filename)

# Check if the model has the attribute to get feature names
if hasattr(loaded_model, 'feature_names_in_'):
    model_feature_names = loaded_model.feature_names_in_.tolist()
    print("Model feature names:", model_feature_names)
else:
    print("Model does not have feature_names_in_ attribute.")

# Example data for prediction with the correct features
data = {
    'Origin': [0],  # Example origin index
    'Destination': [1],  # Example destination index
    'Traffic_Delay': [0.5],  # Example traffic delay
    'Vehicle_ID': [0],  # Example vehicle index
    'Vehicle_1_Capacity': [1000],  # Example capacity for vehicle 1
    'Vehicle_2_Capacity': [800],  # Example capacity for vehicle 2
    'Vehicle_3_Capacity': [600],  # Example capacity for vehicle 3
    'Vehicle_4_Capacity': [400],  # Example capacity for vehicle 4
    'Vehicle_5_Capacity': [200],  # Example capacity for vehicle 5
    'Load': [300],  # Example load
    'Fuel_Consumption': [0.2],  # Example fuel consumption
    'Latitude_x': [40.74],  # Example latitude (origin)
    'Longitude_x': [-74.01],  # Example longitude (origin)
    'Delivery_Location_ID_x': [0],  # Example delivery location ID (origin)
    'Demand_x': [150],  # Example demand (origin)
    'Latitude_y': [40.74],  # Example latitude (destination)
    'Longitude_y': [-74.01],  # Example longitude (destination)
    'Delivery_Location_ID_y': [1],  # Example delivery location ID (destination)
    'Demand_y': [200],  # Example demand (destination)
    'Delivery_Time_Window_x_Evening': [0],  # Binary for evening window (origin)
    'Delivery_Time_Window_x_Morning': [1],  # Binary for morning window (origin)
    'Delivery_Time_Window_y_Evening': [0],  # Binary for evening window (destination)
    'Delivery_Time_Window_y_Morning': [1]  # Binary for morning window (destination)
}

# Create the DataFrame
input_df = pd.DataFrame(data)

# Display the input DataFrame
print("Input DataFrame:")
print(input_df)

# Make predictions
try:
    predictions = loaded_model.predict(input_df)
    print("Predictions:", predictions)
except Exception as e:
    print("Error during prediction:", e)
```

```
import numpy as np
import pandas as pd
from sklearn.metrics import mean_absolute_error, mean_squared_error, r2_score, confusion_matrix, accuracy_score, f1_score

# Step 1: Define your actual values (y_true) and predicted values (y_pred)
# Replace these with your actual data
y_true = np.array([150, 200, 300, 250, 100])  # Example actual values
y_pred = np.array([155, 195, 295, 240, 90])   # Example predicted values

# Step 2: Calculate regression metrics
mae = mean_absolute_error(y_true, y_pred)
mse = mean_squared_error(y_true, y_pred)
r2 = r2_score(y_true, y_pred)
rmse = np.sqrt(mse)

# Print regression metrics
print("Mean Absolute Error (MAE):", mae)
print("Mean Squared Error (MSE):", mse)
print("Root Mean Squared Error (RMSE):", rmse)
print("R² Score:", r2)

# Step 3: Convert predictions to classes (for binary classification)
# Here we assume a threshold to create classes (0 or 1)
mean_value = np.mean(y_true)
y_true_classes = [1 if value >= mean_value else 0 for value in y_true]
y_pred_classes = [1 if value >= mean_value else 0 for value in y_pred]

# Step 4: Calculate confusion matrix and classification metrics
cm = confusion_matrix(y_true_classes, y_pred_classes)
accuracy = accuracy_score(y_true_classes, y_pred_classes)
f1 = f1_score(y_true_classes, y_pred_classes, average='weighted')  # Use 'macro' or 'micro' as needed

# Print classification metrics
print("Confusion Matrix:\n", cm)
print("Accuracy:", accuracy)
print("F1 Score:", f1)
```

### Output:

![Screenshot 2024-11-05 055509](https://github.com/user-attachments/assets/eb3a149a-28a3-4902-a5ce-0b73a8948830)
![Screenshot 2024-11-05 055633](https://github.com/user-attachments/assets/2bf65faf-ba48-46f4-8ae8-84c0a17c643d)


### Result:
Thus the system was trained successfully and the prediction was carried out.
