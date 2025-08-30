# Trustworthy Location Reviews

A machine learning system for detecting and classifying review quality based on spam, advertisement, irrelevance, and rant detection.

## Team
- **Team Name:** Code Fellas
- **Team Members:** Rayaan Nabi Ahmed Quraishi, Kunal Soni

## Overview

This project implements an automated system to evaluate the trustworthiness of location-based reviews. The system identifies reviews that violate content policies including spam, advertisements, irrelevant content, and user rants, then provides a quality score for each review.

## Features

- **Multi-label Classification**: Detects spam, advertisements, rants, and irrelevant content
- **Location Tagging**: Automatically categorizes business locations (restaurant, office, home, etc.)
- **Policy Enforcement**: Applies configurable content policies to reviews
- **Quality Scoring**: Generates composite quality scores based on multiple factors
- **Semantic Analysis**: Uses sentence transformers for relevance detection

## Dataset

The system processes review data with the following structure:
- Business name
- Author name  
- Review text
- Photo path
- Rating (1-5)
- Rating category
- Location type (auto-generated)

## Methodology

### 1. Data Labeling
- **Location Classification**: Uses Google Flan-T5 model for location type inference
- **Semantic Relevance**: Employs sentence transformers to measure text-location similarity
- **Keyword Detection**: Rule-based detection for spam, ads, and rants
- **Quality Fusion**: Combines multiple signals into a unified quality score

### 2. Policy Enforcement
- Merges review labels with configurable policy definitions
- Supports flexible policy rules via JSON configuration
- Outputs policy-compliant datasets

### 3. Text Classification
- **Ensemble Learning**: Random Forest with multi-output classification
- **Feature Engineering**: Text normalized - lowercase, word segmentation, special character removal. 
- **Balanced Splitting**: Iterative stratification for multi-label data
- **Evaluation Metrics**: Precision, recall, and F1-score per class

## Installation

```bash
# Clone the repository
git clone https://github.com/your-repo/trustworthy-location-reviews.git
cd trustworthy-location-reviews

# Install required packages
pip install torch pandas numpy transformers sentence-transformers
pip install scikit-learn scikit-multilearn
```

## Files
- input: "reviews.csv"
- output: "data.csv"
- policies: "policies.json"
- output with policy: "data_w_policy.csv"
