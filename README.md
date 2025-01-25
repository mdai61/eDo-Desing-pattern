Predicting H1 Target for November 2024: A Predictive Modeling Project with OOP and Design Patterns
Overview
This project extends the previous implementation of predictive modeling to forecast the target in the H1 (1-hour) timeframe for November 2024. While the underlying objective and data remain the same, this project focuses on incorporating object-oriented programming (OOP) principles and software design patterns to improve code structure, reusability, and maintainability.
The key objectives include:
1.	Forecasting the target categories based on historical OHLCV data resampled into the H1 timeframe.
2.	Leveraging OOP principles (abstraction, inheritance, polymorphism, encapsulation) to structure the codebase.
3.	Using design patterns such as the Template Method, Strategy, and Decorator to organize the workflow and enhance flexibility.
________________________________________
Target Categories
The target categories are based on the percentage change in the Close price over the next 10 H1 candles:
•	A: (< -5%)
•	B: (-5% to -2%)
•	C: (-2% to +2%)
•	D: (+2% to +5%)
•	E: (> +5%)
Additionally, a momentum target based on the Relative Strength Index (RSI) was also implemented.
________________________________________
Dataset
The dataset remains the same and is provided as a CSV file containing historical M1 (1-minute) OHLCV data, which was resampled into H1 data. Key features include:
•	OHLCV: Open, High, Low, Close, Volume values aggregated over 1-hour intervals.
•	Engineered Features: Lagged values, moving averages, and RSI-based momentum metrics.
________________________________________
Improvements in This Project
Object-Oriented Programming (OOP) Principles
The project has been refactored to follow OOP best practices, such as:
•	Encapsulation: Code is modularized into classes with specific responsibilities.
•	Inheritance: Shared functionality is implemented in abstract base classes (BaseTrainer, BaseVisualizer) and extended in concrete classes (e.g., XGBoostTrainer, XGBoostVisualizer).
•	Polymorphism: The training and visualization processes are dynamically handled through abstract base classes, enabling easy extensibility.
•	Abstraction: High-level classes define workflows, leaving specific implementation details to subclasses.
Design Patterns
Several design patterns were implemented to improve code structure:
1.	Template Method Pattern:
o	The BaseTrainer class defines a high-level workflow for model training (preprocessing, training, evaluation, logging).
o	Specific implementations are handled by subclasses (e.g., XGBoostTrainer).
2.	Strategy Pattern:
o	Training strategies are encapsulated in separate trainer classes (e.g., XGBoostTrainer), allowing easy swapping or extension of models.
3.	Decorator Pattern:
o	A log_results decorator dynamically adds logging functionality to evaluation methods without modifying their core logic.
These patterns enhance code maintainability, readability, and extensibility, making the project easier to modify and scale for new use cases.
________________________________________
Approach
Preprocessing
•	Resampled the M1 data into H1 format using Pandas.
•	Engineered lag features, moving averages, and RSI-based metrics.
•	Defined two targets:
1.	Target 1: Percentage change in Close price over the next 10 H1 candles.
2.	Target 2: Momentum target based on RSI values.
Feature Selection
•	Variance Inflation Factor (VIF) was used to eliminate multicollinear features.
Modeling
•	The dataset was split into train and test sets, with test data corresponding to November 2024.
•	XGBoost was selected as the primary model for Target 1 predictions.
Evaluation
•	Model performance was evaluated using RMSE, R², and a confusion matrix.
•	Visualizations, including time-series plots and confusion matrices, were generated for interpretability.
________________________________________
Results
•	Confusion Matrix: Evaluated the model’s performance on Target 1 predictions for November 2024.
•	Best Model: XGBoost provided the best accuracy and interpretability for the task.
•	Visualization: Dynamic and static plots were generated for the train-test split and prediction targets.
________________________________________
Tools and Libraries Used
Programming Language
•	Python
Libraries
•	Pandas: Data processing and resampling.
•	NumPy: Numerical computations.
•	Seaborn & Matplotlib: Visualization.
•	Scikit-learn: Feature selection and evaluation metrics.
•	XGBoost: Model training and prediction.
________________________________________
Key Differences from the Previous Project
1.	Code Refactoring:
o	The code was restructured into modular components using OOP principles.
o	Abstract base classes (BaseTrainer, BaseVisualizer) were introduced for better scalability.
2.	Design Patterns:
o	Implemented Template Method, Strategy, and Decorator patterns to organize workflows and add flexibility.
3.	Enhanced Maintainability:
o	The modular design allows for easy addition of new models, features, or visualizations without impacting existing functionality.
________________________________________
Getting Started
How to Run the Project
1.	Clone the repository:
bash
CopyEdit
git clone <repository-url>
cd project
2.	Install dependencies:
bash
CopyEdit
pip install -r requirements.txt
3.	Run the project:
bash
CopyEdit
python main.py

