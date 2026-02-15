# Agro-Waste to Fragrance AI - Design Document

## Project Overview

**Project Name:** Agro-Waste to Fragrance AI  
**Tagline:** Transforming Agricultural Waste into Sustainable Fragrance Opportunities  
**Version:** 1.0  
**Last Updated:** February 15, 2026

---

## Executive Summary

The Agro-Waste to Fragrance AI system is a comprehensive platform that transforms agricultural waste analysis into actionable fragrance production recommendations. The system employs a six-layer architecture combining computer vision, machine learning, and predictive analytics to provide farmers and cooperatives with economic and environmental insights.

The platform processes agro-waste images through a sophisticated pipeline: image preprocessing, computer vision analysis for waste classification and feature extraction, ML-based fragrance potential scoring, hybrid recommendation generation, predictive analytics for economic and environmental impact assessment, and comprehensive result presentation with GPS tracking, rewards, and feedback mechanisms.

---

## 1. System Architecture

### 1.1 High-Level Architecture Overview

```
┌─────────────────────────────────────────────────────────────────────────────────────────────────┐
│                          AGRO-WASTE TO FRAGRANCE AI SYSTEM ARCHITECTURE                         │
├─────────────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                                 │
│  ┌──────────────────┐  ┌──────────────────┐  ┌──────────────────┐  ┌──────────────────┐      │
│  │  USER INTERFACE  │  │   API GATEWAY    │  │  AI PROCESSING   │  │   DATA LAYER     │      │
│  │      LAYER       │  │      LAYER       │  │      CORE        │  │                  │      │
│  ├──────────────────┤  ├──────────────────┤  ├──────────────────┤  ├──────────────────┤      │
│  │ Web Application  │  │ /upload          │  │ Input Layer      │  │ PostgreSQL       │      │
│  │ React.js         │  │ /analyze         │  │ Image Preproc    │  │ User Data        │      │
│  │ Dashboard        │  │ /recommend       │  │ GPS Capture      │  │ Analysis Results │      │
│  │                  │  │ /rewards         │  │                  │  │ Audit Logs       │      │
│  │ Mobile App       │  │ /feedback        │  │ Computer Vision  │  │                  │      │
│  │ iOS/Android      │  │                  │  │ CNN/ViT Models   │  │ MongoDB          │      │
│  │ Image Upload     │  │ FastAPI /        │  │ Classification   │  │ Image Metadata   │      │
│  │ GPS Enabled      │  │ Node.js          │  │ Feature Extract  │  │ Location Data    │      │
│  │                  │  │                  │  │                  │  │                  │      │
│  │ Third-Party      │  │ Authentication   │  │ ML Analysis      │  │ Redis Cache      │      │
│  │ API Clients      │  │ Rate Limiting    │  │ Fragrance Score  │  │ Session Data     │      │
│  │ REST/GraphQL     │  │ Load Balancing   │  │ Quality Grade    │  │ Rate Limiting    │      │
│  │                  │  │                  │  │                  │  │                  │      │
│  │                  │  │                  │  │ Recommendation   │  │ AWS S3           │      │
│  │                  │  │                  │  │ Product Mapping  │  │ Image Storage    │      │
│  │                  │  │                  │  │ Economic Rank    │  │ Model Storage    │      │
│  │                  │  │                  │  │                  │  │ Report Storage   │      │
│  │                  │  │                  │  │ Predictive       │  │                  │      │
│  │                  │  │                  │  │ Economic Model   │  │                  │      │
│  │                  │  │                  │  │ Environmental    │  │                  │      │
│  │                  │  │                  │  │ Impact Calc      │  │                  │      │
│  │                  │  │                  │  │                  │  │                  │      │
│  │                  │  │                  │  │ Output Layer     │  │                  │      │
│  │                  │  │                  │  │ Report Gen       │  │                  │      │
│  │                  │  │                  │  │ Visualization    │  │                  │      │
│  └──────────────────┘  └──────────────────┘  └──────────────────┘  └──────────────────┘      │
│                                                                                                 │
│  ┌─────────────────────────────────────────────────────────────────────────────────────────┐  │
│  │                              SUPPORTING SERVICES                                        │  │
│  ├─────────────────────────────────────────────────────────────────────────────────────────┤  │
│  │  GPS Tracking  │  Rewards Engine  │  Feedback System  │  Model Management  │  Notify  │  │
│  │  Location      │  Points Calc     │  Rating Collect   │  Training Pipeline │  Email   │  │
│  │  Geocoding     │  Tier Manager    │  Feedback Analyze │  Version Control   │  SMS     │  │
│  │  Privacy Mgmt  │  Leaderboards    │  Model Improve    │  A/B Testing       │  Push    │  │
│  └─────────────────────────────────────────────────────────────────────────────────────────┘  │
│                                                                                                 │
│  ┌─────────────────────────────────────────────────────────────────────────────────────────┐  │
│  │                              EXTERNAL SERVICES                                          │  │
│  ├─────────────────────────────────────────────────────────────────────────────────────────┤  │
│  │  Market Data API  │  Geocoding API  │  Payment Gateway  │  Cloud Storage  │  Analytics │  │
│  └─────────────────────────────────────────────────────────────────────────────────────────┘  │
│                                                                                                 │
└─────────────────────────────────────────────────────────────────────────────────────────────────┘
```

### 1.2 Component Details

#### 1.2.1 User Interface Layer

| Component | Technology | Description |
|-----------|------------|-------------|
| Web Application | React.js, TypeScript | Dashboard for farmers and cooperatives to upload waste images |
| Mobile App | React Native | iOS/Android app with camera integration and GPS |
| API Clients | REST/GraphQL | Third-party integration interfaces |

#### 1.2.2 API Gateway Layer

| Endpoint | Purpose |
|----------|---------|
| `/upload` | Image and metadata upload handling |
| `/analyze` | Trigger AI analysis pipeline |
| `/recommend` | Retrieve fragrance recommendations |
| `/rewards` | Rewards and points management |
| `/feedback` | User feedback submission |

**Framework:** FastAPI / Node.js  
**Features:** Authentication, Rate Limiting, Load Balancing

#### 1.2.3 AI Processing Core

| Component | Technology | Purpose |
|-----------|------------|---------|
| Input Layer | Python, OpenCV | Image preprocessing, GPS capture |
| Computer Vision | CNN/Vision Transformers | Waste classification, feature extraction |
| ML Analysis | Random Forest, XGBoost | Fragrance potential scoring |
| Recommendation | Hybrid ML + Rules | Product mapping and ranking |
| Predictive Analytics | Regression Models | Economic and environmental predictions |
| Output Layer | Python, Jinja2 | Report generation and visualization |

#### 1.2.4 Data Layer

| Component | Technology | Purpose |
|-----------|------------|---------|
| PostgreSQL | Relational DB | User data, analysis results, audit logs |
| MongoDB | Document DB | Image metadata, location data |
| Redis Cache | In-memory store | Session cache, rate limiting |
| AWS S3 | Object storage | Images, models, reports |

#### 1.2.5 Supporting Services

| Service | Type | Purpose |
|---------|------|---------|
| GPS Tracking | Location Service | Capture and analyze geographic data |
| Rewards Engine | Gamification | Points, tiers, leaderboards |
| Feedback System | ML Improvement | User ratings and model retraining |
| Model Management | MLOps | Training, versioning, deployment |
| Notification | Communication | Email, SMS, push notifications |

---

## 2. AI Pipeline Architecture

### 2.1 6-Stage AI Processing Pipeline

```
┌──────────┐    ┌──────────┐    ┌──────────┐    ┌──────────┐    ┌──────────┐    ┌──────────┐
│ STAGE 1  │ -> │ STAGE 2  │ -> │ STAGE 3  │ -> │ STAGE 4  │ -> │ STAGE 5  │ -> │ STAGE 6  │
│  INPUT   │    │ COMPUTER │    │    ML    │    │  RECOM   │    │ PREDICT  │    │  OUTPUT  │
│  LAYER   │    │  VISION  │    │ ANALYSIS │    │  SYSTEM  │    │ ANALYTICS│    │  LAYER   │
└──────────┘    └──────────┘    └──────────┘    └──────────┘    └──────────┘    └──────────┘
     │               │               │               │               │               │
     v               v               v               v               v               v
  Upload          Classify       Score &         Map to          Economic        Generate
  Image +         Waste +        Grade          Products +       & Environ       Reports +
  GPS Data        Extract        Fragrance      Rank by          Impact          Rewards
                  Features       Potential      Viability        Metrics
```

### 2.2 Pipeline Stage Details

#### Stage 1: Input Layer
**Input:** Raw agro-waste images (JPEG/PNG/TIFF) + GPS coordinates  
**Processing:**
- Image validation and format checking
- Resize to standard dimensions (224x224)
- Pixel normalization [0,1]
- Data augmentation (rotation, brightness, contrast)
- GPS coordinate extraction and validation

**Output:** Preprocessed image tensor + location metadata

---

#### Stage 2: Computer Vision Module
**Input:** Preprocessed image tensor  
**Processing:**
- CNN/Vision Transformer classification
- Waste category identification (fruit peels, grain husks, flower waste, etc.)
- Texture feature extraction (LBP, Gabor filters)
- Color histogram analysis
- Confidence score calculation

**Output:** Waste category + confidence score + feature vectors

---

#### Stage 3: ML Analysis Engine
**Input:** Feature vectors + waste category  
**Processing:**
- Random Forest/XGBoost prediction
- Fragrance potential scoring (0-100)
- Quality grade assignment (A/B/C/D)
- Confidence interval calculation

**Output:** Fragrance potential score + quality grade + confidence intervals

---

#### Stage 4: Recommendation System
**Input:** Waste category + fragrance score + quality grade  
**Processing:**
- Rule-based product mapping
- Essential oil suitability analysis
- Incense production feasibility
- Aromatic extract potential
- Economic viability ranking

**Output:** Ranked fragrance product recommendations + processing methods

---

#### Stage 5: Predictive Analytics Module
**Input:** Recommendations + market data + location  
**Processing:**
- Income estimation per kilogram
- Processing cost calculation
- Net profit projection
- CO₂ emissions avoided calculation
- Carbon sequestration estimation
- Regional market insights

**Output:** Economic projections + environmental impact metrics

---

#### Stage 6: Output & Impact Layer
**Input:** All analysis results  
**Processing:**
- Result aggregation
- Report generation (PDF)
- Visualization creation
- Rewards points calculation
- Notification preparation

**Output:** Comprehensive report + rewards + notifications

---

## 3. Supporting Systems Architecture

### 3.1 GPS Tracking Module

```
┌─────────────────────────────────────────────────────────────────┐
│                    GPS TRACKING MODULE                          │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ┌──────────────┐    ┌──────────────┐    ┌──────────────┐    │
│  │   CAPTURE    │ -> │   VALIDATE   │ -> │   ANALYZE    │    │
│  ├──────────────┤    ├──────────────┤    ├──────────────┤    │
│  │ EXIF Data    │    │ Lat/Lng      │    │ Heat Maps    │    │
│  │ Device GPS   │    │ Range Check  │    │ Distribution │    │
│  │ Manual Entry │    │ Geocoding    │    │ Regional     │    │
│  │ IP Geoloc    │    │ Privacy Mgmt │    │ Insights     │    │
│  └──────────────┘    └──────────────┘    └──────────────┘    │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

**Components:**
- **LocationService:** GPS capture and validation
- **GeographicAnalyzer:** Waste distribution mapping
- **PrivacyManager:** User consent and data anonymization

---

### 3.2 Rewards Engine

```
┌─────────────────────────────────────────────────────────────────┐
│                      REWARDS ENGINE                             │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ┌──────────────┐    ┌──────────────┐    ┌──────────────┐    │
│  │ EARN POINTS  │ -> │  TIER MGMT   │ -> │   REDEEM     │    │
│  ├──────────────┤    ├──────────────┤    ├──────────────┤    │
│  │ Upload: 1-10 │    │ Bronze: 0-   │    │ Equipment    │    │
│  │ Quality: +   │    │   100        │    │ Discounts    │    │
│  │ Referral: 50 │    │ Silver: 101- │    │ Cash         │    │
│  │ Feedback:    │    │   500        │    │ Vouchers     │    │
│  │   10-20      │    │ Gold: 501-   │    │ Carbon       │    │
│  │ Milestone: + │    │   1000       │    │ Credits      │    │
│  │              │    │ Platinum:    │    │              │    │
│  │              │    │   1000+      │    │              │    │
│  └──────────────┘    └──────────────┘    └──────────────┘    │
│                                                                 │
│  ┌──────────────────────────────────────────────────────────┐  │
│  │              LEADERBOARDS & ACHIEVEMENTS                 │  │
│  │  Regional Rankings | Global Rankings | Achievement Badges│  │
│  └──────────────────────────────────────────────────────────┘  │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

**Components:**
- **PointsCalculator:** Award points based on actions
- **TierManager:** Manage user progression through tiers
- **RedemptionService:** Handle reward redemptions
- **LeaderboardManager:** Maintain rankings

---

### 3.3 Feedback System

```
┌─────────────────────────────────────────────────────────────────┐
│                     FEEDBACK SYSTEM                             │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ┌──────────────┐    ┌──────────────┐    ┌──────────────┐    │
│  │   COLLECT    │ -> │   ANALYZE    │ -> │   IMPROVE    │    │
│  ├──────────────┤    ├──────────────┤    ├──────────────┤    │
│  │ 5-Star       │    │ Aggregate    │    │ Model        │    │
│  │ Rating       │    │ Stats        │    │ Retraining   │    │
│  │ Comments     │    │ Pattern      │    │ A/B Testing  │    │
│  │ Outcome Data │    │ Detection    │    │ Validation   │    │
│  │ (Yield,      │    │ Error        │    │ Deployment   │    │
│  │  Income,     │    │ Flagging     │    │              │    │
│  │  Quality)    │    │ Expert       │    │              │    │
│  │              │    │ Review       │    │              │    │
│  └──────────────┘    └──────────────┘    └──────────────┘    │
│                                                                 │
│                    ┌─────────────────────┐                     │
│                    │  Bonus Points for   │                     │
│                    │  Detailed Feedback  │                     │
│                    └─────────────────────┘                     │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

**Components:**
- **RatingCollector:** Capture user feedback
- **FeedbackAnalyzer:** Analyze patterns and trends
- **ModelImprovementLoop:** Retrain models with feedback
- **FeedbackIncentivizer:** Reward users for feedback

---

---

## 4. Components and Interfaces

### Input Layer Components

**ImageProcessor**
- Validates image formats (JPEG, PNG, TIFF)
- Resizes images to standard dimensions (224x224 for CNN compatibility)
- Normalizes pixel values to [0,1] range
- Applies data augmentation when enabled

**DataValidator**
- Validates image quality and resolution
- Checks file size constraints
- Ensures metadata completeness

**GPSCapture**
- Extracts GPS coordinates from image EXIF data
- Validates latitude/longitude ranges (-90 to 90, -180 to 180)
- Captures timestamp and altitude when available
- Handles missing GPS data gracefully with fallback options

### Computer Vision Module Components

**WasteClassifier**
- Implements CNN or Vision Transformer architecture
- Classifies waste into predefined categories (fruit peels, grain husks, flower waste, etc.)
- Returns classification with confidence scores

**FeatureExtractor**
- Extracts texture features using Local Binary Patterns and Gabor filters
- Analyzes color histograms and dominant color extraction
- Generates high-dimensional feature vectors for ML analysis

### ML Analysis Engine Components

**FragrancePotentialPredictor**
- Uses Random Forest or Gradient Boosting models
- Predicts fragrance potential scores (0-100)
- Trained on historical fragrance production datasets

**QualityGrader**
- Maps fragrance potential scores to quality grades (A: 80-100, B: 60-79, C: 40-59, D: 0-39)
- Provides confidence intervals for predictions

### Recommendation System Components

**ProductMapper**
- Rule-based mapping of waste types to fragrance products
- Essential oil recommendations for high-oil content waste
- Incense recommendations for fibrous materials
- Aromatic extract suggestions for flower-based waste

**EconomicRanker**
- Ranks recommendations by economic viability
- Considers processing costs and market prices
- Incorporates seasonal demand variations

### Predictive Analytics Module Components

**EconomicPredictor**
- Regression models for income estimation per kilogram
- Incorporates current market prices and processing costs
- Provides confidence intervals and seasonal adjustments

**EnvironmentalImpactCalculator**
- Calculates CO₂ emissions avoided by preventing waste burning
- Estimates carbon sequestration benefits from fragrance production
- Compares against baseline disposal methods

### Output & Impact Layer Components

**ResultAggregator**
- Combines results from all analysis modules
- Prioritizes recommendations based on multiple criteria

**ReportGenerator**
- Creates comprehensive PDF reports
- Generates visualizations and charts
- Formats data for different user types

### GPS Tracking Module Components

**LocationService**
- Captures GPS coordinates from device or image metadata
- Validates geographic coordinates
- Geocodes coordinates to human-readable addresses
- Stores location history for waste source tracking

**GeographicAnalyzer**
- Analyzes waste distribution patterns by region
- Provides location-specific market insights
- Generates heat maps of waste sources
- Identifies regional fragrance production opportunities

**PrivacyManager**
- Manages user location privacy settings
- Anonymizes location data when required
- Implements location data retention policies
- Provides opt-in/opt-out controls for location tracking

### Rewards Engine Components

**PointsCalculator**
- Awards points based on image quality (1-10 points)
- Grants bonus points for complete metadata (5 points)
- Provides milestone bonuses for sustainability achievements
- Calculates referral bonuses (50 points per successful referral)

**TierManager**
- Manages reward tiers (Bronze: 0-100, Silver: 101-500, Gold: 501-1000, Platinum: 1000+)
- Tracks user progression through tiers
- Unlocks tier-specific benefits and features
- Sends tier upgrade notifications

**RedemptionService**
- Manages reward catalog (equipment discounts, cash vouchers, carbon credits)
- Processes reward redemptions
- Tracks redemption history
- Integrates with payment and fulfillment systems

**LeaderboardManager**
- Maintains regional and global leaderboards
- Updates rankings in real-time
- Displays top contributors by various metrics
- Implements fair ranking algorithms

### Feedback System Components

**RatingCollector**
- Presents rating forms after analysis completion
- Collects 5-star ratings with optional comments
- Captures outcome feedback (actual yield, income, quality)
- Timestamps all feedback submissions

**FeedbackAnalyzer**
- Aggregates feedback statistics
- Identifies systematic errors and patterns
- Flags low-rated analyses for expert review
- Generates accuracy trend reports

**ModelImprovementLoop**
- Feeds user feedback into model retraining pipelines
- Weights feedback by user reliability and expertise
- Tracks model performance improvements over time
- Implements A/B testing for model updates

**FeedbackIncentivizer**
- Awards bonus points for detailed feedback (10-20 points)
- Encourages outcome reporting with rewards
- Gamifies feedback submission
- Tracks user feedback contribution history

---

## 5. Data Models

### Core Data Structures

**WasteImage**
```
{
  id: string
  userId: string
  imageData: binary
  metadata: {
    uploadTimestamp: datetime
    location: coordinates
    wasteType: string (optional)
    quantity: number (optional)
  }
  processingStatus: enum [uploaded, processing, completed, failed]
}
```

**AnalysisResult**
```
{
  imageId: string
  classification: {
    wasteCategory: string
    confidence: number
    alternativeCategories: array[{category: string, confidence: number}]
  }
  featureVector: array[number]
  fragrancePotential: {
    score: number
    grade: enum [A, B, C, D]
    confidenceInterval: {lower: number, upper: number}
  }
  timestamp: datetime
}
```

**FragranceRecommendation**
```
{
  analysisId: string
  recommendations: array[{
    productType: enum [essential_oil, incense, aromatic_extract]
    suitabilityScore: number
    processingMethod: string
    estimatedYield: number
    economicViability: number
  }]
  rankedByPriority: boolean
}
```

**EconomicProjection**
```
{
  analysisId: string
  incomeEstimate: {
    perKilogram: number
    confidenceInterval: {lower: number, upper: number}
    seasonalAdjustment: number
  }
  processingCosts: {
    equipment: number
    labor: number
    utilities: number
  }
  netProfit: number
  marketFactors: {
    currentPrices: object
    demandTrends: array[number]
  }
}
```

**EnvironmentalImpact**
```
{
  analysisId: string
  co2EmissionsAvoided: {
    fromBurningPrevention: number
    fromFragranceProduction: number
    total: number
    unit: string
  }
  carbonSequestration: number
  sustainabilityMetrics: {
    wasteReductionPercentage: number
    energySavings: number
    waterUsageReduction: number
  }
  carbonCreditEstimate: number
}
```

**LocationData**
```
{
  imageId: string
  coordinates: {
    latitude: number
    longitude: number
    altitude: number (optional)
    accuracy: number
  }
  address: {
    country: string
    state: string
    district: string
    locality: string
  }
  timestamp: datetime
  source: enum [gps, exif, manual, ip_geolocation]
  privacyLevel: enum [public, anonymized, private]
}
```

**UserRewards**
```
{
  userId: string
  totalPoints: number
  currentTier: enum [bronze, silver, gold, platinum]
  tierProgress: {
    currentPoints: number
    nextTierThreshold: number
    percentageComplete: number
  }
  pointsHistory: array[{
    points: number
    reason: string
    timestamp: datetime
    relatedImageId: string (optional)
  }]
  achievements: array[{
    badgeId: string
    badgeName: string
    earnedAt: datetime
    description: string
  }]
  redemptions: array[{
    redemptionId: string
    rewardType: string
    pointsSpent: number
    redeemedAt: datetime
    status: enum [pending, fulfilled, cancelled]
  }]
}
```

**UserFeedback**
```
{
  feedbackId: string
  userId: string
  analysisId: string
  rating: number (1-5)
  comment: string (optional)
  outcomeData: {
    actualYield: number (optional)
    actualIncome: number (optional)
    actualQuality: string (optional)
    processingMethod: string (optional)
  }
  feedbackType: enum [recommendation_accuracy, prediction_accuracy, user_experience]
  submittedAt: datetime
  reviewStatus: enum [pending, reviewed, flagged]
  pointsAwarded: number
}
```

**Leaderboard**
```
{
  leaderboardId: string
  region: string
  period: enum [daily, weekly, monthly, all_time]
  rankings: array[{
    rank: number
    userId: string
    userName: string (anonymized if privacy enabled)
    totalPoints: number
    totalSubmissions: number
    co2Avoided: number
  }]
  lastUpdated: datetime
}
```

### Database Schema

**Users Table**
- id (primary key)
- email, name, userType
- apiKey (for programmatic access)
- createdAt, lastLogin

**Images Table**
- id (primary key)
- userId (foreign key)
- filePath, originalName
- metadata (JSON)
- uploadedAt, processedAt

**Analyses Table**
- id (primary key)
- imageId (foreign key)
- results (JSON containing all analysis data)
- processingTime, createdAt

**Models Table**
- id (primary key)
- modelType, version
- filePath, performance metrics
- isActive, deployedAt

**Locations Table**
- id (primary key)
- imageId (foreign key)
- latitude, longitude, altitude
- address (JSON)
- timestamp, source, privacyLevel

**Rewards Table**
- id (primary key)
- userId (foreign key)
- totalPoints, currentTier
- tierProgress (JSON)
- pointsHistory (JSON)
- achievements (JSON)
- redemptions (JSON)

**Feedback Table**
- id (primary key)
- userId (foreign key)
- analysisId (foreign key)
- rating, comment
- outcomeData (JSON)
- feedbackType, submittedAt
- reviewStatus, pointsAwarded

**Leaderboards Table**
- id (primary key)
- region, period
- rankings (JSON)
- lastUpdated

---

## 6. Correctness Properties

*A property is a characteristic or behavior that should hold true across all valid executions of a system—essentially, a formal statement about what the system should do. Properties serve as the bridge between human-readable specifications and machine-verifiable correctness guarantees.*

### Property 1: Image Processing Consistency
*For any* uploaded image file, if it has a valid format (JPEG, PNG, TIFF), then the preprocessing pipeline should produce an output with standard dimensions, normalized pixel values in [0,1] range, and appropriate augmentation when enabled.
**Validates: Requirements 1.1, 1.2, 1.3, 1.5**

### Property 2: Image Quality Validation
*For any* image with insufficient quality metrics (resolution, clarity, file corruption), the system should reject the image and return a descriptive error message explaining the quality issue.
**Validates: Requirements 1.4**

### Property 3: Computer Vision Classification Completeness
*For any* processed image, the computer vision module should produce a classification result containing a valid waste category from the predefined set, confidence score, and properly dimensioned feature vectors.
**Validates: Requirements 2.1, 2.2, 2.3**

### Property 4: Confidence-Based Uncertainty Flagging
*For any* classification result with confidence score below 70%, the system should automatically flag the result as uncertain and include this flag in the output.
**Validates: Requirements 2.4**

### Property 5: Fragrance Potential Score Bounds
*For any* feature vector input to the ML analysis engine, the predicted fragrance potential score should always fall within the valid range of 0-100, and be accompanied by a properly mapped quality grade (A: 80-100, B: 60-79, C: 40-59, D: 0-39).
**Validates: Requirements 3.1, 3.2**

### Property 6: Grade-Based Processing Recommendations
*For any* analysis result with quality grade A (score 80-100), the system should recommend immediate processing, while grade D results (score 0-40) should recommend alternative uses.
**Validates: Requirements 3.3, 3.4**

### Property 7: Prediction Confidence Intervals
*For any* ML prediction (fragrance potential, economic estimates), the system should provide confidence intervals with the specified confidence level (95% for economic estimates).
**Validates: Requirements 3.5, 5.4**

### Property 8: Waste-to-Product Mapping Completeness
*For any* combination of waste classification and fragrance potential score, the recommendation system should produce a complete mapping to suitable fragrance products with appropriate processing methods and economic viability rankings.
**Validates: Requirements 4.1, 4.5**

### Property 9: Conditional Process Recommendations
*For any* waste analysis indicating high essential oil potential, aromatic compounds, or incense suitability, the system should provide appropriate process recommendations (distillation, extraction, or grinding/binding respectively).
**Validates: Requirements 4.2, 4.3, 4.4**

### Property 10: Economic Analysis Completeness
*For any* completed waste analysis, the predictive analytics module should generate income estimates per kilogram, incorporate available market data, calculate net profit when processing costs are known, and apply seasonal adjustments when variations exist.
**Validates: Requirements 5.1, 5.2, 5.3, 5.5**

### Property 11: Environmental Impact Calculation Completeness
*For any* waste processing scenario, the system should calculate CO₂ emissions avoided from burning prevention, estimate carbon sequestration benefits, provide metrics in standard units, compare against baseline disposal methods, and generate carbon credit estimates when requested.
**Validates: Requirements 6.1, 6.2, 6.3, 6.4, 6.5**

### Property 12: Result Presentation Completeness
*For any* completed analysis, the output layer should present classification results with confidence scores, recommendations ranked by priority, economic projections with visual charts when available, environmental metrics display, and provide PDF report generation capability.
**Validates: Requirements 7.1, 7.2, 7.3, 7.4, 7.5**

### Property 13: Data Security and Persistence
*For any* data operation (image upload, result storage, user data handling), the system should ensure secure storage with user consent, persist analysis results for future reference, encrypt sensitive information, apply retention policies with automatic purging, and maintain comprehensive audit logs.
**Validates: Requirements 8.1, 8.2, 8.3, 8.4, 8.5**

### Property 14: Model Lifecycle Management
*For any* model management operation, the system should handle automatic retraining when new data is available or performance degrades, validate model performance against test datasets, maintain version history for rollback capabilities, and support A/B testing for model comparison.
**Validates: Requirements 9.1, 9.2, 9.3, 9.4, 9.5**

### Property 15: API Compliance and Security
*For any* API interaction, the system should provide RESTful endpoints following standard conventions, authenticate requests using API keys, return responses in valid JSON format, implement rate limiting to prevent abuse, and provide comprehensive OpenAPI documentation.
**Validates: Requirements 10.1, 10.2, 10.3, 10.4, 10.5**

### Property 16: GPS Location Capture and Validation
*For any* image upload with available GPS data, the system should capture and store valid geographic coordinates (latitude: -90 to 90, longitude: -180 to 180), timestamp, and optional altitude, while respecting user privacy settings and allowing graceful handling when GPS is unavailable.
**Validates: Requirements 11.1, 11.2, 11.3, 11.4, 11.7**

### Property 17: Location-Based Insights
*For any* analysis with valid location data, the system should provide region-specific fragrance market insights and include geographic distribution information in generated reports.
**Validates: Requirements 11.5, 11.6**

### Property 18: Rewards Points Calculation
*For any* valid waste image submission, the system should award points based on image quality and metadata completeness, with bonus points for high-quality waste and successful analysis completion.
**Validates: Requirements 12.1, 12.2**

### Property 19: Rewards Tier Management
*For any* user's accumulated points, the system should correctly assign reward tiers (Bronze: 0-100, Silver: 101-500, Gold: 501-1000, Platinum: 1000+), send notifications upon tier changes, and unlock appropriate tier-specific benefits.
**Validates: Requirements 12.3, 12.4, 12.5**

### Property 20: Rewards Redemption and Referrals
*For any* reward redemption request, the system should validate sufficient points, process redemptions for available options (equipment discounts, cash vouchers, carbon credits), track redemption history, and award referral bonuses when applicable.
**Validates: Requirements 12.6, 12.7**

### Property 21: Leaderboards and Achievements
*For any* user activity, the system should maintain accurate regional and global leaderboards, update rankings appropriately, and award achievement badges when sustainability milestones are reached.
**Validates: Requirements 12.8, 12.9**

### Property 22: Feedback Collection and Rating
*For any* completed analysis, the system should provide feedback mechanisms allowing users to rate recommendations on a 5-star scale with optional comments, request outcome feedback, and store all feedback with associated analysis data.
**Validates: Requirements 13.1, 13.2, 13.3, 13.4**

### Property 23: Feedback-Driven Improvement
*For any* submitted feedback, the system should flag negative ratings for expert review, use feedback data for model retraining, award bonus points for detailed feedback, and trigger alerts when systematic errors are detected.
**Validates: Requirements 13.5, 13.6, 13.7, 13.9**

### Property 24: Feedback Transparency and History
*For any* user or system administrator, the system should display aggregate feedback statistics showing accuracy trends and provide users with access to their feedback history including past ratings and outcomes.
**Validates: Requirements 13.8, 13.10**

---

## 7. Error Handling

The system implements comprehensive error handling across all layers:

**Input Layer Error Handling:**
- Invalid image formats return HTTP 400 with specific format requirements
- Oversized files return HTTP 413 with size limit information
- Corrupted images return HTTP 422 with quality assessment details
- Missing metadata returns HTTP 400 with required field specifications

**Computer Vision Module Error Handling:**
- Model inference failures trigger fallback to simpler classification models
- Feature extraction errors return partial results with confidence penalties
- GPU memory issues automatically switch to CPU processing with performance warnings
- Classification confidence below threshold triggers human review workflows

**ML Analysis Engine Error Handling:**
- Missing training data triggers model retraining workflows
- Prediction outliers are flagged and require manual validation
- Model performance degradation triggers automatic rollback to previous versions
- Feature vector dimension mismatches return detailed error diagnostics

**Recommendation System Error Handling:**
- Missing market data triggers fallback to historical averages with uncertainty flags
- Invalid waste-product mappings return alternative recommendations with explanations
- Economic calculation errors provide partial results with identified missing components
- Ranking failures return unranked recommendations with warning messages

**Data Layer Error Handling:**
- Database connection failures trigger automatic retry with exponential backoff
- Storage quota exceeded returns HTTP 507 with cleanup recommendations
- Encryption failures prevent data storage and return security error messages
- Audit log failures trigger system alerts and temporary operation suspension

**API Error Handling:**
- Authentication failures return HTTP 401 with clear authentication requirements
- Rate limit exceeded returns HTTP 429 with retry-after headers
- Malformed requests return HTTP 400 with detailed validation error messages
- Internal server errors return HTTP 500 with correlation IDs for debugging

**GPS Tracking Error Handling:**
- Missing GPS data allows image upload to proceed with location marked as unavailable
- Invalid coordinates (out of range) return HTTP 400 with valid range specifications
- GPS permission denied by user stores image without location data
- Geocoding service failures fall back to coordinate-only storage
- Privacy setting conflicts prevent location storage and notify user

**Rewards Engine Error Handling:**
- Points calculation errors default to minimum valid points with error logging
- Tier progression failures maintain current tier and trigger manual review
- Redemption failures (insufficient points, unavailable rewards) return HTTP 400 with clear messages
- Leaderboard update failures trigger background retry with exponential backoff
- Achievement badge assignment errors log failures without blocking user workflow

**Feedback System Error Handling:**
- Invalid rating values (outside 1-5 range) return HTTP 400 with valid range
- Feedback submission failures retry automatically up to 3 times
- Model retraining triggered by feedback handles failures gracefully with rollback
- Feedback analysis errors flag data for manual review without blocking submissions
- Missing outcome data allows partial feedback submission with optional fields marked

---

## 8. Testing Strategy

The system employs a comprehensive dual testing approach combining unit tests and property-based tests to ensure correctness and reliability.

**Property-Based Testing Configuration:**
- Minimum 100 iterations per property test to ensure statistical significance
- Each property test references its corresponding design document property
- Tag format: **Feature: agro-waste-fragrance-ai, Property {number}: {property_text}**
- Property tests focus on universal behaviors across all valid inputs
- Random input generation covers edge cases and boundary conditions

**Unit Testing Focus Areas:**
- Specific examples demonstrating correct behavior for known inputs
- Integration points between system components
- Edge cases and error conditions not covered by property tests
- Performance benchmarks for critical operations
- Mock external dependencies (market data APIs, cloud storage)

**Testing Framework Selection:**
- **Python**: Hypothesis for property-based testing, pytest for unit tests
- **TypeScript/JavaScript**: fast-check for property-based testing, Jest for unit tests
- **Java**: jqwik for property-based testing, JUnit 5 for unit tests

**Test Data Management:**
- Synthetic image generation for computer vision testing
- Historical fragrance production data for ML model validation
- Mock market data APIs for economic prediction testing
- Anonymized real-world waste images for integration testing
- Synthetic GPS coordinates covering global geographic ranges
- Mock user reward data for tier progression testing
- Simulated feedback datasets for model improvement validation

**Continuous Testing Pipeline:**
- Property tests run on every commit with full 100-iteration cycles
- Unit tests execute in parallel for faster feedback
- Integration tests run on staging environment with real data subsets
- Performance tests execute nightly with trend analysis
- Model accuracy tests run weekly against held-out validation datasets
- GPS validation tests verify coordinate ranges and privacy compliance
- Rewards calculation tests ensure point accuracy and tier thresholds
- Feedback loop tests validate model improvement from user input

**Test Coverage Requirements:**
- Minimum 90% code coverage for core business logic
- 100% coverage for data validation and security functions
- Property test coverage for all correctness properties
- Integration test coverage for all API endpoints
- End-to-end test coverage for critical user workflows
- GPS privacy and security test coverage at 100%
- Rewards calculation accuracy tests with edge cases
- Feedback system integration tests with ML retraining pipeline