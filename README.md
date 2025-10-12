# Mobile Price Predictor Web App

A Flask-based web application that predicts mobile phone prices based on specifications using machine learning. The app replicates the preprocessing pipeline from the `Model_training.ipynb` notebook and provides a user-friendly interface for price prediction.

## Features

- **Interactive Web Interface**: Clean, modern UI with Bootstrap styling
- **Complete Preprocessing Pipeline**: Replicates all data cleaning and preprocessing steps from the notebook
- **Real-time Predictions**: Instant price predictions based on user input
- **Responsive Design**: Works on desktop and mobile devices
- **Input Validation**: Form validation with helpful error messages
- **Sample Data**: Quick-fill button for testing with sample data

## Model Details

- **Algorithm**: SGD Regressor (Stochastic Gradient Descent)
- **Features**: 13 input features including physical specs, display, camera, storage, and performance
- **Preprocessing**: 
  - Missing value imputation
  - Outlier detection and treatment using IQR method
  - Categorical encoding with custom mappings
  - Standard scaling for numerical features
- **Performance**: R² Score: 0.3302, RMSE: 5893.04

## Input Features

### Physical Specifications
- **Weight (grams)**: Phone weight
- **Battery Capacity (mAh)**: Battery capacity

### Display Specifications
- **Display Type**: IPS, TFT, Capacitive, AMOLED, Super AMOLED
- **Display Resolution**: Screen resolution
- **Display Size PPI**: Pixels per inch

### Connectivity & Storage
- **SIM Type**: Single or Dual SIM
- **Memory Card Support (GB)**: Expandable storage capacity
- **Internal Memory (GB)**: Built-in storage
- **RAM (GB)**: Random Access Memory

### Camera & Performance
- **Primary Camera (MP)**: Main camera megapixels
- **Secondary Camera (MP)**: Front camera megapixels
- **CPU Type**: Dual-core, Quad-core, Hexa-core, Octa-core
- **Operating System**: Android versions (Ice Cream Sandwich to Nougat)

## Installation & Setup

### Prerequisites
- Python 3.8 or higher
- pip (Python package installer)

### Step 1: Clone or Download
```bash
# If you have the files locally, navigate to the project directory
cd D:\Temp\MLOB1
```

### Step 2: Create Virtual Environment (Recommended)
```bash
# Create virtual environment
python -m venv mobile_price_env

# Activate virtual environment
# On Windows:
mobile_price_env\Scripts\activate
# On macOS/Linux:
source mobile_price_env/bin/activate
```

### Step 3: Install Dependencies
```bash
pip install -r requirements.txt
```

### Step 4: Run the Application
```bash
python app.py
```

The application will start on `http://localhost:5000` or `http://127.0.0.1:5000`

## Usage

1. **Open the Web App**: Navigate to `http://localhost:5000` in your browser
2. **Fill the Form**: Enter mobile phone specifications in the form fields
3. **Use Sample Data**: Click "Fill Sample Data" button to test with pre-filled values
4. **Get Prediction**: Click "Predict Price" to get the estimated price
5. **View Results**: The predicted price will be displayed in EUR format

## File Structure

```
MLOB1/
├── app.py                          # Main Flask application
├── requirements.txt                # Python dependencies
├── templates/
│   └── index.html                  # HTML template with form
├── Sessions/
│   └── Day15/
│       ├── Model_training.ipynb    # Original training notebook
│       ├── regression_mobile_price.csv  # Training dataset
│       └── sgd_regressor_model.pkl # Trained model file
└── README.md                       # This file
```

## API Endpoints

### GET /
- **Description**: Serves the main web interface
- **Response**: HTML page with prediction form

### POST /predict
- **Description**: Processes form data and returns price prediction
- **Request**: Form data with mobile specifications
- **Response**: JSON with prediction result or error message

Example response:
```json
{
    "success": true,
    "predicted_price": 250.45,
    "predicted_price_formatted": "€250.45"
}
```

## Customization

### Adding New Features
1. Update the form in `templates/index.html`
2. Modify the preprocessing function in `app.py`
3. Retrain the model if needed

### Styling Changes
- Modify the CSS in the `<style>` section of `templates/index.html`
- Update Bootstrap classes for different styling

### Model Updates
1. Retrain the model using `Model_training.ipynb`
2. Save the new model file
3. Update the model loading path in `app.py`

## Troubleshooting

### Common Issues

1. **Module Not Found Error**
   - Ensure all dependencies are installed: `pip install -r requirements.txt`
   - Check if virtual environment is activated

2. **Model File Not Found**
   - Ensure `sgd_regressor_model.pkl` exists in `Sessions/Day15/`
   - Check file paths in `app.py`

3. **Port Already in Use**
   - Change the port in `app.py`: `app.run(port=5001)`
   - Or kill the process using port 5000

4. **Prediction Errors**
   - Check input data format and ranges
   - Ensure all required fields are filled
   - Verify categorical values match expected options

### Debug Mode
To enable debug mode for development:
```python
app.run(debug=True)
```

## Performance Notes

- The preprocessing pipeline replicates the exact same steps as the training notebook
- StandardScaler is fitted on the original training data for consistency
- Outlier detection uses the same IQR method as in training
- Categorical encoding uses the same mappings as defined in the notebook

## Future Enhancements

- Add more mobile phone brands and models
- Implement model retraining with new data
- Add confidence intervals for predictions
- Include feature importance visualization
- Add data export functionality
- Implement user authentication and prediction history

## License

This project is part of the Machine Learning course materials. Please refer to the main project license for usage terms.

## Support

For issues or questions:
1. Check the troubleshooting section above
2. Verify all dependencies are correctly installed
3. Ensure the model file exists and is accessible
4. Check the console output for error messages