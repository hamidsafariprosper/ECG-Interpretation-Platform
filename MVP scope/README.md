MVP scope:
Take a smartphone photo of ECG strip, interprete if STEMI or Normal

PIPELINE ARCHITECTURE
1. Image preprocessing: Crop ECG borders
2. Signal reconstruction
3. AI classification model: Input, ECG photos, Model: 2D CNN (ResNet-18 or MobileNet, pre-trained on ImageNet → fine-tune on ECGs), output: binary, STEMI or No STEMI

MODEL PROTOTYPE AND TRAINING
Framework: PyTorch (easy for research), TensorFlow Lite (easy for mobile).
Steps:
1. Starting with transfer learning (ResNet / EfficientNet).
2. Train with 10–20k labeled ECG images.
3. Augment with random blur, rotation, brightness changes.
4. Evaluate on test set → track accuracy, sensitivity, specificity.
Goal for MVP: ≥80% sensitivity for STEMI.

5. Mobile App Prototype
A basic app that:
1. Opens camera → capture ECG photo.
2. Sends image to AI model (either local inference or cloud).
3. Displays result:
Green = No STEMI
Red = Possible STEMI → Seek urgent care

