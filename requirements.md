# AgniShakti: AI-Powered Fire Detection & Emergency Response System for Bharat

## 1. Project Overview

AgniSetu (Sanskrit: "Fire Bridge") is an intelligent, real-time fire detection and emergency response platform designed to address India's critical fire safety infrastructure gap. Leveraging computer vision (YOLOv8) and generative AI (Google Gemini), the system transforms ordinary surveillance cameras into intelligent fire sentinels, providing automated detection, verification, and coordinated emergency response.

**Core Innovation**: Dual-AI verification architecture combining edge-optimized object detection with cloud-based contextual analysis to achieve 95%+ accuracy while minimizing false positives—a critical requirement for emergency systems.

**Bharat-Centric Design**: Built for India's diverse infrastructure landscape, from urban high-rises to rural industrial facilities, with support for low-bandwidth environments, multilingual interfaces, and integration with existing CCTV infrastructure.

**Social Impact**: Addresses the alarming reality that India records over 25,000 fire-related deaths annually (NCRB 2022), with response times averaging 15-20 minutes in urban areas and significantly longer in rural regions. AgniSetu reduces detection-to-alert time from minutes to seconds.

## 2. Problem Statement

### 2.1 Current Challenges in India

**Infrastructure Gaps**:
- Only 2,500 fire stations serve 1.4 billion people (1 station per 560,000 citizens vs. global standard of 1:50,000)
- 70% of fire stations lack modern detection equipment
- Manual fire detection relies on human vigilance, leading to delayed response

**Response Time Crisis**:
- Average fire station response time: 15-20 minutes (urban), 30+ minutes (rural)
- Critical "golden window" for fire suppression: 3-5 minutes
- Delayed detection accounts for 60% of fire-related fatalities

**Technology Adoption Barriers**:
- Existing fire detection systems (smoke detectors, thermal cameras) cost ₹50,000-₹5,00,000 per installation
- Limited coverage in residential, small business, and rural settings
- No integration between detection systems and emergency response networks

**Verification Challenges**:
- False alarms constitute 40-60% of fire department calls, wasting critical resources
- Lack of contextual information delays appropriate response deployment
- No automated triage system for emergency prioritization

### 2.2 Urgency & Scale

- **25,000+ annual fire deaths** (NCRB 2022)
- **₹25,000 crore annual economic loss** from fire incidents
- **Growing urbanization**: 600+ million urban residents by 2030, increasing fire risk density
- **Industrial expansion**: 63 million MSMEs with minimal fire safety infrastructure

## 3. Objectives & Goals

### 3.1 Primary Objectives

1. **Democratize Fire Safety**: Enable any property owner with existing CCTV cameras to deploy AI-powered fire detection at <10% cost of traditional systems

2. **Reduce Response Time**: Achieve <30 second detection-to-alert pipeline, reducing emergency response initiation time by 90%

3. **Minimize False Positives**: Maintain <5% false positive rate through dual-AI verification, ensuring emergency resources are deployed efficiently

4. **Enable Coordinated Response**: Automatically notify property owners, nearest fire stations, and emergency contacts with precise location data and visual evidence

### 3.2 Measurable Goals (12-Month Horizon)

- **Deployment**: 10,000+ camera installations across 5 states
- **Coverage**: Protect 500,000+ citizens in residential and commercial properties
- **Response Time**: Reduce average detection-to-alert time to <30 seconds
- **Accuracy**: Achieve 95%+ true positive rate, <5% false positive rate
- **Cost Efficiency**: Deliver solution at ₹5,000-₹10,000 per camera (vs. ₹50,000+ for traditional systems)
- **Lives Saved**: Prevent 100+ fire-related casualties through early detection

### 3.3 Social Impact Goals

- **Rural Inclusion**: Deploy in 100+ rural industrial facilities and agricultural warehouses
- **MSME Protection**: Provide affordable fire safety to 1,000+ small businesses
- **Government Integration**: Partner with 10+ municipal fire departments for direct alert integration
- **Awareness**: Train 5,000+ property owners and security personnel on system usage

## 4. Target Users & Stakeholders

### 4.1 Primary Users

**Property Owners** (Residential & Commercial):
- Urban apartment complexes and gated communities
- Small and medium businesses (retail, manufacturing, warehousing)
- Educational institutions (schools, colleges)
- Healthcare facilities (clinics, nursing homes)
- Religious and cultural institutions

**Fire Departments & Emergency Services**:
- Municipal fire stations (urban and semi-urban)
- Industrial fire brigades
- Disaster management authorities

**Security Personnel & Facility Managers**:
- Building security teams
- Industrial safety officers
- Property management companies

### 4.2 Secondary Stakeholders

**Government Bodies**:
- National Disaster Management Authority (NDMA)
- State Fire Services Departments
- Smart City Mission authorities
- Ministry of Housing and Urban Affairs

**Insurance Companies**:
- Property and casualty insurers seeking risk mitigation
- Premium reduction programs for AI-monitored properties

**Technology Partners**:
- CCTV manufacturers and installers
- Telecom providers (for connectivity)
- Cloud service providers

## 5. Functional Requirements

### 5.1 Core AI Detection Features

**FR-1: Real-Time Fire & Smoke Detection**
- Analyze video streams at 1 FPS minimum (configurable based on bandwidth)
- Detect fire and smoke with YOLOv8 model (confidence threshold: 0.75)
- Support multiple camera feeds per property (up to 20 cameras)
- Process frames at edge (local) or cloud based on connectivity

**FR-2: Dual-AI Verification System**
- Primary detection: YOLOv8 object detection (fire/smoke classification)
- Secondary verification: Google Gemini multimodal AI for contextual analysis
- Gemini evaluates: flame characteristics, smoke patterns, environmental context, false positive indicators
- Verification completes within 5-10 seconds of initial detection

**FR-3: Intelligent Alert Management**
- 30-second user cancellation window before emergency notification
- Automatic alert escalation if not cancelled
- Simultaneous notification to: property owner, nearest fire station, emergency contacts
- Alert includes: detection timestamp, camera location, confidence score, snapshot image, GPS coordinates

**FR-4: Multi-Camera Monitoring**
- Centralized dashboard for monitoring multiple properties
- Individual camera start/stop controls
- Real-time camera status indicators (active, inactive, detecting)
- Historical alert log with image evidence

**FR-5: Emergency Response Coordination**
- Automatic identification of nearest fire station using Haversine distance calculation
- Email alerts with embedded location maps (Google Maps integration)
- Alert cooldown system (10 minutes) to prevent notification spam
- Priority-based alert routing (confirmed fire > suspected smoke)

### 5.2 User Management Features

**FR-6: Role-Based Access Control**
- Owner role: Property and camera management, alert monitoring
- Provider role: Fire station dashboard, multi-property alert monitoring
- Admin role: System configuration, user management

**FR-7: Property & Camera Management**
- Add/edit/delete properties with GPS coordinates
- Register cameras with labels and stream sources (RTSP, webcam, WebRTC)
- Assign monitoring passwords for secure camera access
- Automatic nearest fire station assignment based on property location

**FR-8: Fire Station Registration & Management**
- Secure provider registration with verification
- Station profile: name, address, contact details, GPS coordinates
- Dashboard showing all properties within service area
- Real-time alert feed with property details

### 5.3 Integration & Interoperability

**FR-9: Camera Source Compatibility**
- Support RTSP streams (IP cameras)
- Support USB webcams (local installations)
- Support WebRTC streams (browser-based cameras)
- Support video file upload for testing and training

**FR-10: Notification Channels**
- Email notifications (primary)
- SMS alerts (future scope)
- Mobile push notifications (future scope)
- WhatsApp Business API integration (future scope)

**FR-11: Data Export & Reporting**
- Export alert history (CSV, PDF)
- Generate incident reports with timestamps and images
- Analytics dashboard: detection frequency, false positive rate, response times

## 6. Non-Functional Requirements

### 6.1 Performance Requirements

**NFR-1: Detection Latency**
- Frame capture to YOLO inference: <2 seconds
- YOLO detection to Gemini verification: <10 seconds
- Total detection-to-alert pipeline: <30 seconds
- Dashboard alert display: <5 seconds from alert creation

**NFR-2: Throughput & Scalability**
- Support 10,000+ concurrent camera streams
- Handle 1,000+ simultaneous alerts
- Process 100,000+ frames per hour (distributed architecture)
- Scale horizontally with cloud infrastructure

**NFR-3: Availability & Reliability**
- System uptime: 99.5% (excluding planned maintenance)
- Alert delivery success rate: 99%
- Automatic failover for critical services
- Graceful degradation under high load

### 6.2 Usability & Accessibility

**NFR-4: User Experience**
- Dashboard load time: <3 seconds
- Intuitive UI requiring <10 minutes training
- Mobile-responsive design (smartphones, tablets)
- Multilingual support: Hindi, English, Tamil, Telugu, Bengali (Phase 1)

**NFR-5: Accessibility Compliance**
- WCAG 2.1 Level AA compliance
- Screen reader compatibility
- Keyboard navigation support
- High-contrast mode for visually impaired users

### 6.3 Security & Privacy

**NFR-6: Data Security**
- End-to-end encryption for video streams (TLS 1.3)
- Encrypted storage for snapshots (AES-256)
- Secure authentication (Firebase Auth with email/password)
- Role-based access control (RBAC) for all resources

**NFR-7: Privacy Protection**
- No continuous video recording (frame-by-frame analysis only)
- Automatic deletion of snapshots after 30 days
- User consent for data collection and processing
- Compliance with IT Act 2000 and Digital Personal Data Protection Act 2023

**NFR-8: API Security**
- Rate limiting: 100 requests/minute per user
- API key authentication for external integrations
- Input validation and sanitization
- Protection against SQL injection, XSS, CSRF attacks

### 6.4 Maintainability & Extensibility

**NFR-9: Code Quality**
- Modular architecture with clear separation of concerns
- Comprehensive API documentation (OpenAPI/Swagger)
- Unit test coverage: >70%
- Integration test coverage: >50%

**NFR-10: Monitoring & Observability**
- Real-time system health monitoring
- Error logging and alerting (Sentry/CloudWatch)
- Performance metrics tracking (response times, throughput)
- Audit logs for all critical operations

## 7. Data Requirements & Data Sources

### 7.1 Training Data Requirements

**Fire & Smoke Dataset**:
- **Volume**: 50,000+ labeled images (fire: 25,000, smoke: 25,000)
- **Diversity**: Indoor/outdoor, day/night, various lighting conditions
- **Indian Context**: Images from Indian buildings, vehicles, industrial settings
- **Sources**: 
  - Public datasets: FIRE-DB, VisiFire, Foggia Fire Dataset
  - Custom collection: Collaboration with fire departments for real incident footage
  - Synthetic data: Augmentation techniques (rotation, scaling, color jittering)

**Negative Samples (False Positive Reduction)**:
- Sunset/sunrise scenes (orange/red hues)
- Cooking activities (stoves, grills)
- Lighting fixtures (lamps, candles)
- Reflections and glare
- **Volume**: 30,000+ images

### 7.2 Operational Data

**Camera Metadata**:
- Camera ID, label, location (GPS), stream source
- Installation date, last active timestamp
- Owner information (encrypted)

**Alert Data**:
- Detection timestamp, camera ID, confidence score
- Bounding box coordinates, snapshot image
- Gemini verification results (JSON)
- Alert status (pending, confirmed, rejected, cancelled)
- Response timestamps (alert sent, fire station notified)

**User Data**:
- Email (normalized), name, role
- Property addresses and GPS coordinates
- Fire station assignments
- Alert history and preferences

### 7.3 Data Storage & Retention

**Firestore Collections**:
- `users`: User profiles and authentication
- `houses`: Property information and monitoring settings
- `cameras`: Camera configurations and status
- `fireStations`: Fire station profiles and service areas
- `alerts`: Alert records with detection metadata

**Cloud Storage**:
- Detection snapshots: 30-day retention
- Model artifacts: YOLOv8 weights, configuration files
- Backup data: Weekly snapshots, 90-day retention

### 7.4 Data Privacy & Compliance

**Anonymization**:
- No personally identifiable information (PII) in training data
- Face blurring in detection snapshots (optional feature)
- GPS coordinates rounded to 100m precision for privacy

**Consent & Transparency**:
- Explicit user consent for camera monitoring
- Clear privacy policy and terms of service
- User rights: data access, correction, deletion (DPDP Act 2023)

**Data Localization**:
- All user data stored in Indian data centers (Mumbai, Hyderabad regions)
- Compliance with data localization requirements

## 8. AI/ML Requirements

### 8.1 Primary Detection Model (YOLOv8)

**Model Specifications**:
- Architecture: YOLOv8n (nano) or YOLOv8s (small) for edge deployment
- Input: 640x640 RGB images
- Output: Bounding boxes, class labels (fire, smoke), confidence scores
- Inference time: <100ms on GPU, <500ms on CPU

**Training Requirements**:
- Framework: PyTorch, Ultralytics YOLOv8
- Training data: 50,000+ labeled images (fire, smoke)
- Augmentation: Random rotation, flip, brightness, contrast
- Hyperparameters: Batch size 16, learning rate 0.01, epochs 100
- Validation split: 80% train, 10% validation, 10% test

**Performance Targets**:
- Precision: >90% (minimize false positives)
- Recall: >95% (minimize false negatives—critical for safety)
- mAP@0.5: >0.90
- Inference latency: <500ms per frame

**Model Optimization**:
- Quantization: INT8 for edge devices (TensorRT, ONNX)
- Pruning: Remove redundant weights for faster inference
- Model distillation: Compress to <10MB for mobile deployment

### 8.2 Verification Model (Google Gemini)

**Model Selection**:
- Primary: Gemini 2.0 Flash (fast, cost-effective)
- Fallback: Gemini 1.5 Flash, Gemini 1.5 Pro

**Verification Prompt**:
```
Analyze this image for fire or smoke. Provide:
1. isFire: true/false (is this a real fire/smoke?)
2. score: 0.0-1.0 (confidence)
3. reason: Detailed explanation
4. fireIndicators: List of fire characteristics observed
5. falsePositiveReasons: List of reasons if false positive
6. sensitive: true/false (contains sensitive content?)
7. sensitiveReason: Explanation if sensitive
```

**Response Format**: Structured JSON for programmatic processing

**Performance Targets**:
- Verification latency: <5 seconds
- Accuracy: >98% (reduce false positives from YOLO)
- Cost: <₹0.50 per verification (Gemini Flash pricing)

### 8.3 Edge vs. Cloud Trade-offs

**Edge Deployment (YOLOv8)**:
- **Pros**: Low latency, no internet dependency, privacy-preserving
- **Cons**: Limited compute, requires local GPU/NPU
- **Use Cases**: High-bandwidth environments, privacy-sensitive installations

**Cloud Deployment (YOLOv8 + Gemini)**:
- **Pros**: Scalable, no hardware requirements, easy updates
- **Cons**: Internet dependency, higher latency, data transmission costs
- **Use Cases**: Low-cost installations, remote monitoring

**Hybrid Approach (Recommended)**:
- YOLOv8 on edge for initial detection (low latency)
- Gemini on cloud for verification (high accuracy)
- Fallback to cloud-only if edge compute unavailable

### 8.4 Model Monitoring & Retraining

**Performance Monitoring**:
- Track precision, recall, false positive rate in production
- Log misclassifications for retraining dataset
- A/B testing for model updates

**Retraining Pipeline**:
- Quarterly retraining with new data (seasonal variations, new fire types)
- Continuous learning from user feedback (cancelled alerts = false positives)
- Version control for model artifacts (MLflow, DVC)

## 9. Constraints & Assumptions

### 9.1 Technical Constraints

**Connectivity**:
- Minimum bandwidth: 512 Kbps for 1 FPS video streaming
- Intermittent connectivity: Queue alerts for retry (up to 5 minutes)
- Offline mode: Local detection only, alerts sent when connection restored

**Device Compatibility**:
- Cameras: RTSP-compatible IP cameras, USB webcams
- Browsers: Chrome 90+, Firefox 88+, Safari 14+, Edge 90+
- Mobile: Android 8+, iOS 13+

**Compute Resources**:
- Edge: Raspberry Pi 4 (4GB RAM), NVIDIA Jetson Nano (GPU)
- Cloud: AWS/GCP/Azure with GPU instances (T4, V100)
- Python service: 2GB RAM, 2 vCPU minimum

### 9.2 Operational Constraints

**Deployment Limitations**:
- Requires existing CCTV infrastructure (camera installation not included)
- Internet connectivity mandatory for cloud-based verification
- Email delivery dependent on SMTP service availability

**Regulatory Compliance**:
- No recording of continuous video (privacy regulations)
- User consent required for camera monitoring
- Data localization (Indian servers only)

**Cost Constraints**:
- Target: ₹5,000-₹10,000 per camera installation
- Cloud costs: <₹500/month per camera (compute + storage)
- Gemini API costs: <₹1,000/month for 2,000 verifications

### 9.3 Assumptions

**User Behavior**:
- Property owners have email access and check regularly
- Users will cancel false alarms within 30-second window
- Fire stations will respond to email alerts promptly

**Infrastructure**:
- Existing CCTV cameras have RTSP/HTTP streaming capability
- Internet connectivity available at property location (3G/4G/broadband)
- Fire stations have email infrastructure for alert reception

**Environmental**:
- Cameras have clear view of monitored areas (no obstructions)
- Adequate lighting for visual detection (day/night cameras preferred)
- Cameras positioned at appropriate height and angle

## 10. Success Metrics & KPIs

### 10.1 Technical Performance Metrics

**Detection Accuracy**:
- True Positive Rate (Recall): >95%
- False Positive Rate: <5%
- Precision: >90%
- F1 Score: >0.92

**System Performance**:
- Detection latency: <30 seconds (end-to-end)
- System uptime: >99.5%
- Alert delivery success rate: >99%
- Dashboard response time: <3 seconds

**Scalability**:
- Concurrent camera streams: 10,000+
- Alerts processed per hour: 1,000+
- Users supported: 50,000+

### 10.2 Deployment & Adoption Metrics

**Reach**:
- Camera installations: 10,000+ (Year 1)
- Properties protected: 5,000+ (Year 1)
- Cities covered: 50+ (Year 1)
- Fire stations integrated: 100+ (Year 1)

**User Engagement**:
- Daily active users: 60% of registered users
- Average cameras per property: 3-5
- Alert cancellation rate: <10% (indicates low false positives)
- User retention: >80% after 6 months

### 10.3 Social Impact Metrics

**Lives & Property Saved**:
- Fire incidents detected: 500+ (Year 1)
- Estimated lives saved: 100+ (based on early detection)
- Property damage prevented: ₹50 crore+ (Year 1)
- Response time reduction: 90% (from 15 min to <30 sec detection)

**Cost Efficiency**:
- Cost per installation: <₹10,000 (vs. ₹50,000+ traditional systems)
- Cost per life saved: <₹50,000 (vs. ₹5,00,000+ traditional systems)
- ROI for property owners: 200%+ (insurance savings + damage prevention)

### 10.4 Operational Metrics

**Fire Department Efficiency**:
- False alarm reduction: 60% (from 40-60% to <5%)
- Response time improvement: 30% (better situational awareness)
- Resource utilization: 40% improvement (fewer wasted deployments)

**System Reliability**:
- Mean time between failures (MTBF): >720 hours
- Mean time to recovery (MTTR): <1 hour
- Data loss incidents: 0 (critical alerts)

## 11. Ethical, Privacy & Bias Considerations

### 11.1 Ethical AI Principles

**Transparency**:
- Open documentation of AI models and decision-making process
- Clear explanation of detection confidence scores
- User access to alert history and detection reasoning

**Accountability**:
- Human-in-the-loop: 30-second cancellation window
- Audit trails for all alerts and system actions
- Clear escalation path for disputes and errors

**Fairness**:
- No discrimination based on property type, location, or user demographics
- Equal service quality across urban, semi-urban, and rural areas
- Affordable pricing for low-income users (subsidized plans)

### 11.2 Privacy Protection

**Data Minimization**:
- No continuous video recording (frame-by-frame analysis only)
- Snapshots retained for 30 days only (configurable)
- Automatic deletion of cancelled alerts

**User Control**:
- Users can disable monitoring at any time
- Users can delete their data (right to erasure)
- Users can export their data (right to portability)

**Surveillance Ethics**:
- Clear signage indicating AI-monitored areas
- No facial recognition or people tracking
- Optional face blurring in detection snapshots

### 11.3 Bias Mitigation

**Training Data Diversity**:
- Balanced representation of fire types (residential, industrial, vehicle)
- Diverse lighting conditions (day, night, indoor, outdoor)
- Indian-specific scenarios (festivals, cooking, religious ceremonies)

**Model Fairness Testing**:
- Test across different property types (apartments, houses, warehouses)
- Test across different regions (urban, rural, coastal, mountainous)
- Test across different camera qualities (HD, SD, low-light)

**Continuous Monitoring**:
- Track false positive/negative rates by property type and location
- Identify and correct systematic biases
- Regular model audits by independent third parties

### 11.4 Safety & Harm Prevention

**False Negative Mitigation**:
- High recall (>95%) prioritized over precision
- Multiple detection thresholds for different fire types
- Redundant verification with Gemini AI

**False Positive Management**:
- 30-second cancellation window to prevent unnecessary panic
- 10-minute cooldown to prevent alert fatigue
- User feedback loop to improve model accuracy

**Misuse Prevention**:
- No surveillance features (people tracking, facial recognition)
- Rate limiting to prevent system abuse
- Secure authentication to prevent unauthorized access

## 12. Future Scope & Extensibility

### 12.1 Short-Term Enhancements (6-12 Months)

**Advanced Detection**:
- Gas leak detection (LPG, natural gas)
- Electrical fire prediction (thermal anomalies)
- Explosion risk assessment (pressure vessel monitoring)

**Enhanced Notifications**:
- SMS alerts via Twilio/AWS SNS
- WhatsApp Business API integration
- Mobile push notifications (iOS, Android)
- Voice calls for critical alerts

**Multilingual Support**:
- Expand to 15+ Indian languages
- Voice-based alerts in regional languages
- Localized UI for rural users

**Analytics Dashboard**:
- Fire risk heatmaps by region
- Predictive analytics (fire-prone areas, times)
- Incident trend analysis and reporting

### 12.2 Medium-Term Expansion (1-2 Years)

**Edge AI Deployment**:
- On-device YOLOv8 inference (Raspberry Pi, Jetson)
- Offline detection with cloud sync
- Reduced latency and bandwidth costs

**IoT Integration**:
- Smart smoke detectors (LoRaWAN, NB-IoT)
- Temperature and humidity sensors
- Automatic sprinkler system activation

**Government Integration**:
- Direct integration with fire department dispatch systems
- Integration with Smart City Command Centers
- Integration with National Disaster Management Authority (NDMA)

**Insurance Partnerships**:
- Premium discounts for AI-monitored properties
- Automated claim processing with detection evidence
- Risk assessment and underwriting support

### 12.3 Long-Term Vision (2-5 Years)

**Comprehensive Safety Platform**:
- Multi-hazard detection (fire, flood, earthquake, intrusion)
- Predictive maintenance for fire safety equipment
- AI-powered evacuation route optimization

**Drone Integration**:
- Automated drone dispatch for aerial surveillance
- Real-time fire spread mapping
- Delivery of fire suppression equipment

**Community Safety Network**:
- Crowdsourced fire reporting and verification
- Volunteer firefighter coordination
- Public awareness and training programs

**Research & Development**:
- Federated learning for privacy-preserving model training
- Explainable AI for detection reasoning
- Quantum-resistant encryption for future-proofing

### 12.4 Scalability Roadmap

**Geographic Expansion**:
- Phase 1: 5 states (Maharashtra, Karnataka, Tamil Nadu, Gujarat, Delhi)
- Phase 2: 15 states (all major urban centers)
- Phase 3: Pan-India coverage (including rural and remote areas)

**Vertical Expansion**:
- Residential: Apartments, gated communities
- Commercial: Offices, malls, hotels
- Industrial: Factories, warehouses, refineries
- Infrastructure: Airports, railway stations, metro systems
- Agriculture: Crop storage, livestock facilities

**International Expansion**:
- South Asia: Bangladesh, Sri Lanka, Nepal
- Southeast Asia: Indonesia, Philippines, Vietnam
- Africa: Kenya, Nigeria, South Africa

---

## Document Metadata

**Version**: 1.0  
**Last Updated**: February 15, 2026  
**Authors**: AgniSetu Development Team  
**Hackathon**: AI for Bharat 2026  
**Category**: Public Safety & Emergency Response  
**Tags**: Computer Vision, Fire Detection, Emergency Response, Social Impact, Edge AI

---

## Appendix: References & Resources

**Datasets**:
- FIRE-DB: Fire Detection Dataset (University of Salerno)
- VisiFire: Video Fire Detection Dataset
- Foggia Fire Dataset: Outdoor Fire Detection

**Research Papers**:
- "Real-time Fire Detection using YOLOv8" (2023)
- "Multimodal Fire Verification with Large Language Models" (2024)
- "Edge AI for Emergency Response Systems" (2023)

**Standards & Regulations**:
- National Building Code of India 2016 (Fire Safety)
- IS 2190:2010 (Fire Detection and Alarm Systems)
- IT Act 2000 & Digital Personal Data Protection Act 2023

**Government Initiatives**:
- Smart Cities Mission (Ministry of Housing and Urban Affairs)
- National Disaster Management Plan 2019
- Fire Services Act (State-specific)

---

**Contact**: team@agnisetu.in | www.agnisetu.in  
**GitHub**: github.com/agnisetu/fire-detection  
**Demo**: demo.agnisetu.in
