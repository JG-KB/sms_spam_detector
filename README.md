# SMS Spam Detector

## Background
This project involves refactoring an SMS text classification solution into a function that constructs a **Support Vector Classification (SVC) model**. The trained model is then integrated into a **Gradio app**, allowing users to input text messages and classify them as either "Spam" or "Not Spam".

## Files Included
The following files are included in this repository:
- `gradio_sms_text_classification.ipynb`: Jupyter Notebook that builds the Gradio interface and integrates the classification model.
- `sms_text_classification_solution.ipynb`: Jupyter Notebook containing the initial SMS classification solution.
- `SMSSpamCollection.csv`: Dataset containing labeled SMS messages for training the model.

## Project Setup
Before starting, follow these steps:
1. **Create a new repository** called `sms_spam_detector` on GitHub.
2. **Clone the repository** to your local machine:
   ```bash
   git clone https://github.com/your-username/sms_spam_detector.git
   cd sms_spam_detector
   ```
3. **Add the provided files** to your repository and push changes:
   ```bash
   git add .
   git commit -m "Initial commit"
   git push origin main
   ```

## Implementation Steps
### 1. Create the SMS Classification Function
- Load `SMSSpamCollection.csv` into a Pandas DataFrame.
- Set **features** to the text message column.
- Set **target** to the "label" column.
- Split the dataset into training and testing sets (**test size = 33%**).
- Build a **pipeline** to transform and train the model.
- Fit the model and return the trained classifier (`text_clf`).

### 2. Create the SMS Prediction Function
- Define the `sms_prediction` function to classify new messages.
- Use the trained model to predict the message category.
- If classified as **ham**, return:
  ```
  The text message: "{text}", is not spam.
  ```
- If classified as **spam**, return:
  ```
  The text message: "{text}", is spam.
  ```

### 3. Create the Gradio App
- Use **Gradio** to create a user-friendly interface:
  - Input: Textbox for SMS messages.
  - Output: Textbox displaying the classification result.
- Launch the application and provide a **public URL** for access.

## Running the Gradio App
To run the Gradio app, execute the following command:
```bash
python gradio_sms_text_classification.ipynb
```
This will generate a local and public URL where users can test the classification model.

## Testing the Application
Use the following text samples to test the application:
1. `You are a lucky winner of $5000!`
2. `You won 2 free tickets to the Super Bowl.`
3. `You won 2 free tickets to the Super Bowl. Text us to claim your prize.`
4. `Thanks for registering. Text 4343 to receive free updates on medicare.`

## Dependencies
Ensure the following Python packages are installed:
```bash
pip install pandas scikit-learn gradio
```

## Contribution
Feel free to fork this repository, submit issues, or create pull requests for improvements.

## License
This project is open-source and available under the [MIT License](LICENSE).
