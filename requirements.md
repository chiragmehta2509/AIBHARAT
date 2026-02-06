# Requirements Document

## Introduction

The Agro-Waste to Fragrance AI system is an AI-powered platform that analyzes agro-waste images to recommend suitable fragrance products and predict economic and environmental benefits for farmers and cooperatives. The system transforms agricultural waste into valuable fragrance opportunities while promoting sustainability and providing economic incentives for waste management.

## Glossary

- **System**: The Agro-Waste to Fragrance AI platform
- **Agro_Waste**: Agricultural waste materials that can be processed into fragrance products
- **Fragrance_Product**: Essential oils, incense, or aromatic extracts derived from agro-waste
- **Feature_Vector**: Numerical representation of visual characteristics extracted from waste images
- **Fragrance_Potential_Score**: Numerical rating (0-100) indicating suitability for fragrance production
- **Quality_Grade**: Classification of waste quality (A, B, C, D) based on fragrance potential
- **User**: Farmers, agricultural cooperatives, or sustainability-focused businesses using the system
- **Computer_Vision_Module**: AI component that processes and analyzes waste images
- **ML_Analysis_Engine**: Machine learning component that predicts fragrance potential
- **Recommendation_System**: Component that maps waste types to suitable fragrance products
- **Predictive_Analytics_Module**: Component that estimates economic and environmental benefits

## Requirements

### Requirement 1: Image Input and Processing

**User Story:** As a farmer, I want to upload images of my agro-waste, so that the system can analyze them for fragrance potential.

#### Acceptance Criteria

1. WHEN a user uploads an agro-waste image, THE System SHALL accept common image formats (JPEG, PNG, TIFF)
2. WHEN an image is received, THE System SHALL preprocess it by resizing to standard dimensions
3. WHEN preprocessing occurs, THE System SHALL normalize pixel values for consistent analysis
4. WHEN image quality is insufficient, THE System SHALL return a descriptive error message
5. WHERE image augmentation is enabled, THE System SHALL apply rotation, brightness, and contrast adjustments

### Requirement 2: Computer Vision Analysis

**User Story:** As a system operator, I want the computer vision module to accurately classify waste types, so that appropriate fragrance recommendations can be made.

#### Acceptance Criteria

1. WHEN an image is processed, THE Computer_Vision_Module SHALL classify the waste into predefined categories
2. WHEN classification occurs, THE Computer_Vision_Module SHALL extract texture and color feature vectors
3. WHEN feature extraction completes, THE Computer_Vision_Module SHALL output waste category with confidence score
4. IF classification confidence is below 70%, THEN THE Computer_Vision_Module SHALL flag the result as uncertain
5. THE Computer_Vision_Module SHALL process images within 5 seconds for real-time analysis

### Requirement 3: Fragrance Potential Assessment

**User Story:** As an agricultural cooperative, I want to know the fragrance potential of our waste, so that I can make informed decisions about processing investments.

#### Acceptance Criteria

1. WHEN feature vectors are received, THE ML_Analysis_Engine SHALL predict a Fragrance_Potential_Score between 0-100
2. WHEN scoring completes, THE ML_Analysis_Engine SHALL assign a Quality_Grade based on the score
3. WHEN Quality_Grade is A (score 80-100), THE ML_Analysis_Engine SHALL recommend immediate processing
4. WHEN Quality_Grade is D (score 0-40), THE ML_Analysis_Engine SHALL recommend alternative uses
5. THE ML_Analysis_Engine SHALL provide confidence intervals for all predictions

### Requirement 4: Fragrance Product Recommendations

**User Story:** As a fragrance industry stakeholder, I want specific product recommendations based on waste analysis, so that I can identify suitable raw materials.

#### Acceptance Criteria

1. WHEN waste classification and scoring complete, THE Recommendation_System SHALL map waste types to suitable Fragrance_Products
2. WHEN essential oil potential is high, THE Recommendation_System SHALL recommend distillation processes
3. WHEN aromatic compounds are detected, THE Recommendation_System SHALL suggest extraction methods
4. WHEN waste is suitable for incense, THE Recommendation_System SHALL provide grinding and binding recommendations
5. THE Recommendation_System SHALL rank recommendations by economic viability

### Requirement 5: Economic Impact Prediction

**User Story:** As a farmer, I want to understand the potential income from my waste, so that I can evaluate the economic benefits of fragrance production.

#### Acceptance Criteria

1. WHEN waste analysis completes, THE Predictive_Analytics_Module SHALL estimate expected income per kilogram
2. WHEN market data is available, THE Predictive_Analytics_Module SHALL incorporate current fragrance market prices
3. WHEN processing costs are known, THE Predictive_Analytics_Module SHALL calculate net profit projections
4. THE Predictive_Analytics_Module SHALL provide income estimates with 95% confidence intervals
5. WHEN seasonal variations exist, THE Predictive_Analytics_Module SHALL adjust predictions accordingly

### Requirement 6: Environmental Impact Assessment

**User Story:** As a sustainability-focused business, I want to quantify environmental benefits, so that I can report on carbon footprint reduction.

#### Acceptance Criteria

1. WHEN waste processing alternatives are evaluated, THE Predictive_Analytics_Module SHALL calculate CO₂ emissions avoided by preventing burning
2. WHEN fragrance production occurs, THE Predictive_Analytics_Module SHALL estimate carbon sequestration benefits
3. WHEN environmental calculations complete, THE Predictive_Analytics_Module SHALL provide sustainability metrics in standard units
4. THE Predictive_Analytics_Module SHALL compare environmental impact against baseline waste disposal methods
5. WHEN reporting is requested, THE Predictive_Analytics_Module SHALL generate carbon credit estimates

### Requirement 7: User Interface and Results Presentation

**User Story:** As a user, I want clear and actionable recommendations, so that I can make informed decisions about my agro-waste.

#### Acceptance Criteria

1. WHEN analysis completes, THE System SHALL present waste classification results with confidence scores
2. WHEN recommendations are generated, THE System SHALL display them ranked by priority
3. WHEN economic projections are available, THE System SHALL show income estimates with visual charts
4. WHEN environmental benefits are calculated, THE System SHALL display CO₂ reduction metrics
5. THE System SHALL provide downloadable reports in PDF format for record-keeping

### Requirement 8: Data Management and Storage

**User Story:** As a system administrator, I want secure data handling, so that user information and analysis results are properly managed.

#### Acceptance Criteria

1. WHEN images are uploaded, THE System SHALL store them securely with user consent
2. WHEN analysis results are generated, THE System SHALL persist them for future reference
3. WHEN user data is stored, THE System SHALL encrypt sensitive information
4. WHEN data retention policies apply, THE System SHALL automatically purge expired records
5. THE System SHALL maintain audit logs of all data access and modifications

### Requirement 9: Model Training and Updates

**User Story:** As a data scientist, I want the system to continuously improve, so that recommendation accuracy increases over time.

#### Acceptance Criteria

1. WHEN new training data becomes available, THE System SHALL retrain ML models automatically
2. WHEN model performance degrades, THE System SHALL trigger retraining workflows
3. WHEN model updates occur, THE System SHALL validate performance against test datasets
4. THE System SHALL maintain model versioning for rollback capabilities
5. WHEN A/B testing is enabled, THE System SHALL compare new models against current production models

### Requirement 10: Integration and API Access

**User Story:** As a third-party developer, I want programmatic access to the system, so that I can integrate fragrance analysis into existing agricultural platforms.

#### Acceptance Criteria

1. THE System SHALL provide RESTful API endpoints for image upload and analysis
2. WHEN API requests are made, THE System SHALL authenticate users with API keys
3. WHEN API responses are generated, THE System SHALL return results in JSON format
4. THE System SHALL implement rate limiting to prevent abuse
5. WHEN API documentation is requested, THE System SHALL provide comprehensive OpenAPI specifications

### Requirement 11: GPS Location Tracking

**User Story:** As a farmer, I want to automatically capture the location where waste images are taken, so that the system can provide location-specific recommendations and track waste sources geographically.

#### Acceptance Criteria

1. WHEN a user uploads an image, THE System SHALL capture GPS coordinates from the device
2. WHEN GPS data is available, THE System SHALL store latitude, longitude, and timestamp with the image
3. WHEN location data is captured, THE System SHALL validate coordinates are within valid geographic ranges
4. WHEN GPS is unavailable, THE System SHALL allow manual location entry or proceed without location data
5. THE System SHALL use location data to provide region-specific fragrance market insights
6. WHEN generating reports, THE System SHALL include geographic distribution maps of waste sources
7. THE System SHALL respect user privacy settings for location data sharing

### Requirement 12: Rewards and Incentive System

**User Story:** As a farmer, I want to earn rewards for contributing waste data and adopting sustainable practices, so that I am motivated to participate actively in the platform.

#### Acceptance Criteria

1. WHEN a user uploads a valid waste image, THE System SHALL award points based on image quality and completeness
2. WHEN analysis is completed successfully, THE System SHALL grant bonus points for high-quality waste submissions
3. WHEN users reach point thresholds, THE System SHALL unlock reward tiers (Bronze, Silver, Gold, Platinum)
4. WHEN rewards are earned, THE System SHALL notify users through in-app notifications and email
5. THE System SHALL provide a rewards dashboard showing current points, tier status, and available redemptions
6. WHEN users redeem rewards, THE System SHALL offer options including discounts on processing equipment, cash vouchers, or carbon credits
7. WHEN users refer others to the platform, THE System SHALL award referral bonuses
8. THE System SHALL track and display leaderboards for top contributors by region
9. WHEN sustainability milestones are achieved (e.g., 1 ton CO₂ avoided), THE System SHALL award achievement badges

### Requirement 13: User Feedback and Rating System

**User Story:** As a user, I want to provide feedback on recommendations and rate the accuracy of predictions, so that the system can improve over time and better serve my needs.

#### Acceptance Criteria

1. WHEN analysis results are presented, THE System SHALL provide a feedback form for users to rate recommendation accuracy
2. WHEN users implement recommendations, THE System SHALL request outcome feedback (actual yield, income, quality)
3. WHEN feedback is submitted, THE System SHALL store it with the associated analysis for model improvement
4. THE System SHALL allow users to rate recommendations on a 5-star scale with optional comments
5. WHEN negative feedback is received, THE System SHALL flag the analysis for expert review
6. THE System SHALL use feedback data to retrain and improve ML models automatically
7. WHEN users provide detailed feedback, THE System SHALL award bonus reward points
8. THE System SHALL display aggregate feedback statistics to show system accuracy trends
9. WHEN feedback indicates systematic errors, THE System SHALL trigger alerts to data science teams
10. THE System SHALL provide a feedback history view showing user's past ratings and outcomes