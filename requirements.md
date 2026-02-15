# Agro-Waste to Fragrance AI - Requirements Document

## Project Information

| Field | Details |
|-------|---------|
| **Project Name** | SugandhSetu |
| **Version** | 1.0 |
|**Team Members:**  |Dr Chirag D Mehta, Dr Dikshan N Shah  
| **Last Updated** | February 15, 2026 |
| **Domain** | AI for Agriculture & Sustainability |

---

## 1. Problem Statement

### 1.1 Problem Definition

**Agricultural waste burning in India causes severe environmental and health crises**, with farmers burning over **23 million tonnes of crop residue annually**, contributing to air pollution, climate change, and respiratory diseases affecting millions. Farmers lack awareness and economic incentives to convert waste into valuable products.

### 1.2 Key Statistics

| Metric | Value |
|--------|-------|
| Annual crop residue burned | 23+ million tonnes |
| States most affected | Punjab, Haryana, UP, Delhi NCR |
| Contribution to air pollution | 40-50% during harvest season |
| Economic loss from burning | ₹20,000+ Crore annually |
| Farmers aware of alternatives | Less than 30% |
| CO₂ emissions from burning | 17+ million tonnes/year |
| Potential fragrance market value | ₹5,000+ Crore untapped |

### 1.3 Root Causes

- **Awareness Gap**: 70% of farmers unaware of waste valorization opportunities
- **Economic Barrier**: No clear understanding of income potential from waste
- **Knowledge Gap**: Lack of information on which waste types suit fragrance production
- **Market Access**: Farmers don't know how to connect with fragrance industry buyers
- **Processing Complexity**: Uncertainty about processing methods and costs
- **Environmental Ignorance**: Limited awareness of CO₂ impact from burning

---

## 2. Proposed Solution

### 2.1 Solution Overview

**Agro-Waste to Fragrance AI** is an intelligent platform that analyzes agricultural waste images using computer vision and machine learning to recommend suitable fragrance products (essential oils, incense, aromatic extracts), predict economic returns, and quantify environmental benefits, while gamifying user engagement through rewards and continuous improvement via feedback.

### 2.2 Key Features

| Feature | Description |
|---------|-------------|
| Smart Image Analysis | Upload waste images, AI classifies and extracts visual features |
| Fragrance Potential Scoring | ML models predict fragrance suitability (0-100 score) |
| Product Recommendations | Maps waste to essential oils, incense, or aromatic extracts |
| Economic Projections | Estimates income per kg, processing costs, net profit |
| Environmental Impact | Calculates CO₂ emissions avoided, carbon credits |
| GPS Tracking | Location-based insights and regional market data |
| Rewards System | Gamified points, tiers (Bronze to Platinum), leaderboards |
| Feedback Loop | User ratings improve ML models continuously |
| Multilingual Support | Regional language support for wider accessibility |
| WhatsApp/SMS Delivery | Results delivered via popular messaging platforms |

---

---

## 3. Glossary

| Term | Definition |
|------|------------|
| **System** | The Agro-Waste to Fragrance AI platform |
| **Agro-Waste** | Agricultural waste materials (fruit peels, grain husks, flower waste, etc.) |
| **Fragrance Product** | Essential oils, incense, or aromatic extracts derived from agro-waste |
| **Feature Vector** | Numerical representation of visual characteristics (texture, color) |
| **Fragrance Potential Score** | Numerical rating (0-100) indicating suitability for fragrance production |
| **Quality Grade** | Classification of waste quality (A: 80-100, B: 60-79, C: 40-59, D: 0-39) |
| **User** | Farmers, agricultural cooperatives, or sustainability-focused businesses |
| **Computer Vision Module** | AI component that processes and analyzes waste images |
| **ML Analysis Engine** | Machine learning component that predicts fragrance potential |
| **Recommendation System** | Component that maps waste types to suitable fragrance products |
| **Predictive Analytics Module** | Component that estimates economic and environmental benefits |
| **GPS Tracking** | Location capture and geographic analysis system |
| **Rewards Engine** | Gamification system with points, tiers, and redemptions |
| **Feedback System** | User rating collection and model improvement loop |

---

## 4. Functional Requirements

### 4.1 Core AI Processing Requirements

#### Requirement 1: Image Input and Processing

**User Story:** As a farmer, I want to upload images of my agro-waste, so that the system can analyze them for fragrance potential.

#### Acceptance Criteria

1. WHEN a user uploads an agro-waste image, THE System SHALL accept common image formats (JPEG, PNG, TIFF)
2. WHEN an image is received, THE System SHALL preprocess it by resizing to standard dimensions
3. WHEN preprocessing occurs, THE System SHALL normalize pixel values for consistent analysis
4. WHEN image quality is insufficient, THE System SHALL return a descriptive error message
5. WHERE image augmentation is enabled, THE System SHALL apply rotation, brightness, and contrast adjustments

#### Requirement 2: Computer Vision Analysis

**User Story:** As a system operator, I want the computer vision module to accurately classify waste types, so that appropriate fragrance recommendations can be made.

#### Acceptance Criteria

1. WHEN an image is processed, THE Computer_Vision_Module SHALL classify the waste into predefined categories
2. WHEN classification occurs, THE Computer_Vision_Module SHALL extract texture and color feature vectors
3. WHEN feature extraction completes, THE Computer_Vision_Module SHALL output waste category with confidence score
4. IF classification confidence is below 70%, THEN THE Computer_Vision_Module SHALL flag the result as uncertain
5. THE Computer_Vision_Module SHALL process images within 5 seconds for real-time analysis

#### Requirement 3: Fragrance Potential Assessment

**User Story:** As an agricultural cooperative, I want to know the fragrance potential of our waste, so that I can make informed decisions about processing investments.

#### Acceptance Criteria

1. WHEN feature vectors are received, THE ML_Analysis_Engine SHALL predict a Fragrance_Potential_Score between 0-100
2. WHEN scoring completes, THE ML_Analysis_Engine SHALL assign a Quality_Grade based on the score
3. WHEN Quality_Grade is A (score 80-100), THE ML_Analysis_Engine SHALL recommend immediate processing
4. WHEN Quality_Grade is D (score 0-40), THE ML_Analysis_Engine SHALL recommend alternative uses
5. THE ML_Analysis_Engine SHALL provide confidence intervals for all predictions

#### Requirement 4: Fragrance Product Recommendations

**User Story:** As a fragrance industry stakeholder, I want specific product recommendations based on waste analysis, so that I can identify suitable raw materials.

#### Acceptance Criteria

1. WHEN waste classification and scoring complete, THE Recommendation_System SHALL map waste types to suitable Fragrance_Products
2. WHEN essential oil potential is high, THE Recommendation_System SHALL recommend distillation processes
3. WHEN aromatic compounds are detected, THE Recommendation_System SHALL suggest extraction methods
4. WHEN waste is suitable for incense, THE Recommendation_System SHALL provide grinding and binding recommendations
5. THE Recommendation_System SHALL rank recommendations by economic viability

#### Requirement 5: Economic Impact Prediction

**User Story:** As a farmer, I want to understand the potential income from my waste, so that I can evaluate the economic benefits of fragrance production.

#### Acceptance Criteria

1. WHEN waste analysis completes, THE Predictive_Analytics_Module SHALL estimate expected income per kilogram
2. WHEN market data is available, THE Predictive_Analytics_Module SHALL incorporate current fragrance market prices
3. WHEN processing costs are known, THE Predictive_Analytics_Module SHALL calculate net profit projections
4. THE Predictive_Analytics_Module SHALL provide income estimates with 95% confidence intervals
5. WHEN seasonal variations exist, THE Predictive_Analytics_Module SHALL adjust predictions accordingly

#### Requirement 6: Environmental Impact Assessment

**User Story:** As a sustainability-focused business, I want to quantify environmental benefits, so that I can report on carbon footprint reduction.

#### Acceptance Criteria

1. WHEN waste processing alternatives are evaluated, THE Predictive_Analytics_Module SHALL calculate CO₂ emissions avoided by preventing burning
2. WHEN fragrance production occurs, THE Predictive_Analytics_Module SHALL estimate carbon sequestration benefits
3. WHEN environmental calculations complete, THE Predictive_Analytics_Module SHALL provide sustainability metrics in standard units
4. THE Predictive_Analytics_Module SHALL compare environmental impact against baseline waste disposal methods
5. WHEN reporting is requested, THE Predictive_Analytics_Module SHALL generate carbon credit estimates

---

### 4.2 User Interface and Experience Requirements

#### Requirement 7: User Interface and Results Presentation

**User Story:** As a user, I want clear and actionable recommendations, so that I can make informed decisions about my agro-waste.

#### Acceptance Criteria

1. WHEN analysis completes, THE System SHALL present waste classification results with confidence scores
2. WHEN recommendations are generated, THE System SHALL display them ranked by priority
3. WHEN economic projections are available, THE System SHALL show income estimates with visual charts
4. WHEN environmental benefits are calculated, THE System SHALL display CO₂ reduction metrics
5. THE System SHALL provide downloadable reports in PDF format for record-keeping

---

### 4.3 Data Management and System Requirements

#### Requirement 8: Data Management and Storage

**User Story:** As a system administrator, I want secure data handling, so that user information and analysis results are properly managed.

#### Acceptance Criteria

1. WHEN images are uploaded, THE System SHALL store them securely with user consent
2. WHEN analysis results are generated, THE System SHALL persist them for future reference
3. WHEN user data is stored, THE System SHALL encrypt sensitive information
4. WHEN data retention policies apply, THE System SHALL automatically purge expired records
5. THE System SHALL maintain audit logs of all data access and modifications

#### Requirement 9: Model Training and Updates

**User Story:** As a data scientist, I want the system to continuously improve, so that recommendation accuracy increases over time.

#### Acceptance Criteria

1. WHEN new training data becomes available, THE System SHALL retrain ML models automatically
2. WHEN model performance degrades, THE System SHALL trigger retraining workflows
3. WHEN model updates occur, THE System SHALL validate performance against test datasets
4. THE System SHALL maintain model versioning for rollback capabilities
5. WHEN A/B testing is enabled, THE System SHALL compare new models against current production models

#### Requirement 10: Integration and API Access

**User Story:** As a third-party developer, I want programmatic access to the system, so that I can integrate fragrance analysis into existing agricultural platforms.

#### Acceptance Criteria

1. THE System SHALL provide RESTful API endpoints for image upload and analysis
2. WHEN API requests are made, THE System SHALL authenticate users with API keys
3. WHEN API responses are generated, THE System SHALL return results in JSON format
4. THE System SHALL implement rate limiting to prevent abuse
5. WHEN API documentation is requested, THE System SHALL provide comprehensive OpenAPI specifications

---

### 4.4 Location and Geographic Requirements

#### Requirement 11: GPS Location Tracking

**User Story:** As a farmer, I want to automatically capture the location where waste images are taken, so that the system can provide location-specific recommendations and track waste sources geographically.

#### Acceptance Criteria

1. WHEN a user uploads an image, THE System SHALL capture GPS coordinates from the device
2. WHEN GPS data is available, THE System SHALL store latitude, longitude, and timestamp with the image
3. WHEN location data is captured, THE System SHALL validate coordinates are within valid geographic ranges
4. WHEN GPS is unavailable, THE System SHALL allow manual location entry or proceed without location data
5. THE System SHALL use location data to provide region-specific fragrance market insights
6. WHEN generating reports, THE System SHALL include geographic distribution maps of waste sources
7. THE System SHALL respect user privacy settings for location data sharing

---

### 4.5 Gamification and Engagement Requirements

#### Requirement 12: Rewards and Incentive System

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

---

### 4.6 Continuous Improvement Requirements

#### Requirement 13: User Feedback and Rating System

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

---

## 5. Non-Functional Requirements

### 5.1 Performance Requirements

| Requirement | Target |
|-------------|--------|
| Image processing time | < 5 seconds per image |
| API response time | < 2 seconds for 95th percentile |
| System uptime | 99.5% availability |
| Concurrent users | Support 10,000+ simultaneous users |
| Database query time | < 500ms for 95th percentile |

### 5.2 Security Requirements

| Requirement | Description |
|-------------|-------------|
| Authentication | API key-based authentication for all endpoints |
| Data encryption | AES-256 encryption for data at rest |
| Transport security | TLS 1.3 for data in transit |
| Privacy compliance | GDPR-compliant data handling |
| Location privacy | User-controlled location data sharing |
| Audit logging | Comprehensive audit trails for all operations |

### 5.3 Scalability Requirements

| Requirement | Description |
|-------------|-------------|
| Horizontal scaling | Auto-scaling based on load |
| Database sharding | Support for distributed database architecture |
| CDN integration | Global content delivery for images and reports |
| Load balancing | Distribute traffic across multiple servers |
| Caching strategy | Redis-based caching for frequent queries |

### 5.4 Usability Requirements

| Requirement | Description |
|-------------|-------------|
| Mobile-first design | Responsive UI for mobile devices |
| Multilingual support | Support for 10+ Indian regional languages |
| Accessibility | WCAG 2.1 Level AA compliance |
| Offline capability | Basic functionality without internet |
| Low bandwidth mode | Optimized for 2G/3G networks |

### 5.5 Reliability Requirements

| Requirement | Description |
|-------------|-------------|
| Data backup | Daily automated backups with 30-day retention |
| Disaster recovery | RPO < 1 hour, RTO < 4 hours |
| Error handling | Graceful degradation on component failures |
| Monitoring | Real-time system health monitoring |
| Alerting | Automated alerts for critical failures |

---

## 6. Requirements Summary

### 6.1 Requirements by Category

| Category | Count | Priority |
|----------|-------|----------|
| Core AI Processing | 6 requirements | Critical |
| User Interface | 1 requirement | High |
| Data Management | 3 requirements | High |
| Location & GPS | 1 requirement | Medium |
| Gamification | 1 requirement | Medium |
| Continuous Improvement | 1 requirement | High |
| **Total Functional** | **13 requirements** | - |
| **Non-Functional** | **5 categories** | - |

### 6.2 Success Criteria

| Metric | Target | Timeline |
|--------|--------|----------|
| User adoption | 10,000+ farmers | 6 months |
| Waste analyzed | 100,000+ images | 6 months |
| Classification accuracy | > 90% | Launch |
| Fragrance score accuracy | > 85% | 3 months |
| User satisfaction | > 4.0/5.0 stars | Ongoing |
| CO₂ emissions tracked | 1,000+ tonnes | 6 months |
| Rewards redeemed | 5,000+ redemptions | 6 months |

### 6.3 Out of Scope (Phase 1)

- Direct marketplace for buying/selling waste
- Processing equipment rental/purchase
- Real-time video analysis
- Blockchain-based carbon credit trading
- Integration with government subsidy schemes
- Mobile app for iOS/Android (web-first approach)

---

## 7. Assumptions and Dependencies

### 7.1 Assumptions

1. Users have access to smartphones with cameras
2. Internet connectivity available for image upload (2G minimum)
3. GPS functionality available on user devices
4. Users willing to share location data for insights
5. Market data APIs provide accurate pricing information
6. Historical fragrance production data available for training

### 7.2 Dependencies

| Dependency | Provider | Risk Level |
|------------|----------|------------|
| Cloud infrastructure | AWS/GCP/Azure | Low |
| Computer vision models | TensorFlow/PyTorch | Low |
| LLM API | OpenAI/Anthropic | Medium |
| Market data API | Third-party | Medium |
| Geocoding service | Google Maps API | Low |
| Payment gateway | Razorpay/Stripe | Medium |
| WhatsApp Business API | Meta | Medium |
| SMS gateway | Twilio | Low |

---

## 8. Revision History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | Feb 15, 2026 | Initial Team | Initial requirements document with 13 functional requirements |
| 1.1 | Feb 15, 2026 | Initial Team | Added GPS tracking, rewards, and feedback requirements |