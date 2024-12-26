**Project Requirements Document**

**Project Name:** Park Smart

**Objective:**
To develop a mobile application that identifies and interprets parking rules from photos of parking signs, providing users with clear and accurate information based on the current date, time, and vehicle type.

**Key Features:**

1. **Sign Identification:** Ability to capture and analyze parking sign photos.
2. **Rule Interpretation:** Provide parking rule interpretations based on date and time.
3. **Vehicle-Specific Rules:** Allow users to input their vehicle type for customized results.
4. **Override Option:** Enable users to query specific details manually.
5. **Complex Signage Handling:** Handle multiple signs and identify relevant rules dynamically.
6. **Global Applicability:** Design for universal use, adaptable to local regulations.

**Target Platforms:** Android and iOS (cross-platform development).

---

**User Stories**

**Session 1: Application Structure Setup**

1. As a developer, I want to set up the project structure using React Native or Flutter so that the application is cross-platform.
2. As a developer, I want to integrate the camera functionality to allow users to capture parking sign photos.
3. As a developer, I want to set up a backend service (e.g., Firebase or AWS) for handling image uploads and processing.
4. As a developer, I want to configure the app for deployment to both Android and iOS app stores.

**Session 2: Feature Implementation**

1. As a driver, I want the app to extract text from parking signs using OCR so I can understand the rules.
2. As a driver, I want the app to filter parking rules based on the current date and time for accurate guidance.
3. As a driver, I want to input my vehicle type to determine specific rule applicability.
4. As a driver, I want the app to handle multiple parking signs and prioritize applicable rules.
5. As a developer, I want to implement manual query functionality to allow users to override or clarify results.
6. As a developer, I want to integrate feedback functionality so users can report inaccuracies.

---

**Technical Architecture Document**

**System Overview:**
The application is a cross-platform mobile app developed using React Native or Flutter. It employs a machine learning model to interpret parking signs and integrates with device APIs for camera functionality.

**Technology Stack:**

- **Frontend:** React Native (JavaScript) or Flutter (Dart).
- **Backend:** Firebase or AWS for image processing and storage.
- **Machine Learning Model:**
  - Pre-trained OCR (Optical Character Recognition) for text extraction.
  - Fine-tuned large language model to interpret parking rules based on images.
- **Database:** Firestore or SQLite for storing user data and queries.
- **APIs:** Integration with native camera APIs and optional location services for context.

**Architecture Design:**

1. **Input Layer:** Mobile camera captures the parking sign image.
2. **Processing Layer:**
   - Image sent to backend for OCR.
   - Rules parsed and matched with a predefined dataset.
   - Fine-tuned model interprets complex rule scenarios from extracted text.
3. **Logic Layer:**
   - Apply date, time, and vehicle-specific filters.
   - Return actionable information to the user.
4. **Output Layer:** Display results in an intuitive UI with manual query override options.

**Deployment:**

- Utilize app stores for distribution.
- Support over-the-air updates for non-critical fixes.

---

**Process Flow Document**

**1. Capture:**

- User opens the app and captures a photo of a parking sign.
- Alternatively, they upload an existing photo.

**2. Image Processing:**

- Image sent to backend for OCR and rule extraction.

**3. Rule Matching:**

- OCR output is matched against a database of parking rules.
- Fine-tuned model processes the extracted text to resolve ambiguities.
- Relevant rules are filtered based on current date, time, and user-provided vehicle type.

**4. User Query (Optional):**

- User inputs manual queries to clarify specific details.

**5. Output Results:**

- Results displayed in an easy-to-read format.
- Highlight applicable rules and provide clear guidance.

**6. Feedback (Optional):**

- Users can provide feedback on rule accuracy or report errors.

**End-to-End Flow:**

1. Launch App → 2. Capture/Upload Image → 3. OCR Processing → 4. Rule Interpretation → 5. Display Results → 6. Feedback (Optional).

---

**Behavior-Driven Development (BDD) Test Scenarios**

**Test Scenarios for Session 1: Application Structure Setup**

1. **Scenario:** Verify project setup

   - **Given** a new project is initialized
   - **When** the project structure is created
   - **Then** the application should compile successfully for both Android and iOS.

2. **Scenario:** Test camera integration

   - **Given** the app is running
   - **When** the user accesses the camera
   - **Then** the camera should open and allow capturing an image.

3. **Scenario:** Verify backend setup

   - **Given** a backend is configured
   - **When** an image is uploaded
   - **Then** the backend should accept and store the image.

**Test Scenarios for Session 2: Feature Implementation**

1. **Scenario:** Extract text from a parking sign

   - **Given** a clear image of a parking sign
   - **When** the OCR processes the image
   - **Then** the extracted text should match the text on the sign.

2. **Scenario:** Filter rules based on time

   - **Given** parking rules with time-based restrictions
   - **When** the current time is within the restricted period
   - **Then** the app should indicate parking is not allowed.

3. **Scenario:** Handle multiple signs

   - **Given** multiple parking signs in one image
   - **When** the rules are analyzed
   - **Then** the app should prioritize and display the most restrictive rule.

4. **Scenario:** User query override

   - **Given** a manual query input
   - **When** the user asks about specific rules
   - **Then** the app should display relevant details clearly.

5. **Scenario:** Feedback reporting

   - **Given** a user submits feedback
   - **When** feedback is received
   - **Then** the feedback should be stored for future analysis.

