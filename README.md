# NailAI ✨ 

**Virtually try on nail designs before your next manicure!**

NailVirtuoso is an AI-powered mobile application that allows users to take a picture of their hands and see how different nail art designs would look on their own nails in real-time (or near real-time).

---

## 🎯 Problem Statement

Choosing the perfect nail design can be difficult. Users often struggle to visualize how a specific color, pattern, or art will look on their unique nail shape and skin tone from just a sample photo or swatch. This can lead to disappointment after a manicure.

---

## 💡 Proposed Solution

NailVirtuoso aims to solve this by:

1.  Allowing users to capture an image of their hand(s).
2.  Utilizing advanced AI (Computer Vision and Generative AI) to accurately detect the user's nails.
3.  Intelligently overlaying or generating selected nail designs onto the user's nails in the photo, providing a realistic virtual try-on experience.

---

## ✨ Key Features (MVP - Minimum Viable Product)

*   **📸 Live Camera / Image Upload:** Capture a photo of your hand or upload an existing one.
*   **💅 AI Nail Detection:** Automatic and accurate segmentation of individual nails.
*   **🎨 Curated Design Gallery:** Browse and select from an initial collection of diverse nail designs (e.g., solid colors, simple patterns).
*   **🪄 Virtual Try-On:** See the selected design applied realistically to your nails in the uploaded photo.
*   **🖼️ Result Display:** Clear presentation of the "after" image.

---

## 🛠️ Tech Stack (Planned)

*   **Mobile App (Frontend):** React Native 
*   **Backend & AI:** Python (Flask/FastAPI)
*   **Containerization:** **Docker**
*   **AI Libraries:**
    *   Core Framework: **TensorFlow**
    *   Segmentation: TensorFlow (e.g., U-Net implementation, models from TensorFlow Hub)
    *   Generative Design: TensorFlow (e.g., custom GANs, or if using diffusion models, potentially adapting community implementations or exploring TensorFlow compatible options if they arise)
    *   Image Processing: OpenCV, Pillow, TensorFlow Image (`tf.image`)
*   **Database (Optional - for user accounts/saved designs later):** PostgreSQL/MongoDB 
*   **Cloud Platform: Amazon Web Services (AWS)**
    *   Compute & Container Orchestration: Amazon EC2 (for general backend & GPU instances), **Amazon ECS/EKS (for Docker deployment)**, AWS App Runner, AWS Lambda (with container support)
    *   Container Registry: **Amazon ECR (Elastic Container Registry)**
    *   Storage: Amazon S3 (for datasets, model artifacts, user images)
    *   ML Services: Amazon SageMaker (for model training, deployment, and MLOps pipelines), AWS Rekognition (potential for initial explorations or specific tasks, though custom models will likely be primary)
    *   Database: Amazon RDS (for PostgreSQL/MySQL), Amazon DocumentDB (for MongoDB compatibility)

---

## 🗺️ Project Roadmap

A detailed project roadmap outlining phases from data collection to deployment can be found in [`/docs/ROADMAP.md`](./docs/ROADMAP.md).

**High-Level Phases:**

1.  **Phase 0: Foundations & Planning**
2.  **Phase 1: Data Collection & Preprocessing** (Leveraging "before & after" images from a nail technician)
3.  **Phase 2: Nail Segmentation Model Development (TensorFlow)**
4.  **Phase 3: Generative Model - Design Application (TensorFlow)**
5.  **Phase 4: Backend API Development (Python, Docker, AWS Deployment)**
6.  **Phase 5: Mobile App (Frontend) Development**
7.  **Phase 6: Deployment & Testing (AWS with Docker)**
8.  **Phase 7: Iteration & Future Features**

---

## 🚀 Getting Started

*(This section will be filled out later with installation and usage instructions once parts of the project are functional.)*

**Prerequisites:**

*   **Docker Desktop** (or Docker Engine for Linux) installed.
*   Python 3.x (for local scripting, or if not using Docker for everything locally)
*   TensorFlow 2.x (will be managed by Docker for the backend)
*   AWS Account & AWS CLI configured (for deployment and cloud resource interaction)
*   ...

**Backend Setup & Running (with Docker):**

```bash
# Clone the repository
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name/src/backend # Navigate to your backend directory

# Build the Docker image (assuming you have a Dockerfile here)
docker build -t nailvirtuoso-backend .

# Run the Docker container
# (You'll need to define port mappings, environment variables, volume mounts etc.
#  in your Docker run command or Docker Compose file later)
docker run -p 8000:8000 nailvirtuoso-backend # Example: mapping port 8000
