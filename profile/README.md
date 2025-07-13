# Binary Classification and Prediction System with Voting Mechanism

<div align="center">
  <h2>📚 📥 Download Documentation</h2>
  <p><strong>Access the complete research memo in PDF format</strong></p>
  
  <table>
    <tr>
      <td align="center">
        <h3>🖥️ Digital Version</h3>
        <a href="https://outlierclassifier.github.io/memo/digital.pdf">
          <img src="https://img.shields.io/badge/📄_DIGITAL_PDF-Download_Now-FF6B6B?style=for-the-badge&logo=adobeacrobatreader&logoColor=white&labelColor=2C3E50" alt="Download Digital PDF" height="50"/>
        </a>
        <br><em>Optimized for screen reading</em>
      </td>
      <td width="50"></td>
      <td align="center">
        <h3>🖨️ Print Version</h3>
        <a href="https://outlierclassifier.github.io/memo/print.pdf">
          <img src="https://img.shields.io/badge/📄_PRINT_PDF-Download_Now-4ECDC4?style=for-the-badge&logo=adobeacrobatreader&logoColor=white&labelColor=2C3E50" alt="Download Print PDF" height="50"/>
        </a>
        <br><em>Formatted for physical printing</em>
      </td>
    </tr>
  </table>
</div>

## Overview
Binary classification and prediction system that implements a voting mechanism among multiple machine learning models. The client-server architecture allows processing of temporally and multidimensionally structured data. Each model is implemented as an independent microservice, and is responsible for its own data preprocessing and prediction logic.

## Architecture
The system is divided into modular components:

### Central Server (JavaScript/Node.js)
- Orchestrates requests to the various classification models
- Implements voting mechanisms (initially by majority)
- Provides a visual interface for configuration and visualization
- Manages timeouts and model availability
- Asynchronously handles model responses

### Model Endpoints (Rust/C++)
- Independent APIs implementing six algorithms:
  - SVM
  - LSTM
  - XGBoost
  - One-Class SVM
  - Isolation Forest
  - Custom CNN
- Each model performs its own data preprocessing
- Returns predictions and confidence levels
- Implements healthcheck to verify availability
