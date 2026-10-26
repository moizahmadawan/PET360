# Pet360 — Project Report

## 1. Project title

**Pet360: Smart Pet Care Management System**

**Tagline:** Your pet, Our care.

## 2. Abstract

Pet360 is a mobile application project concept intended to make common pet-care activities easier to organize. It brings together a pet owner's access to pet information, service discovery, a pet-shopping experience, and educational AI demonstrations. The project uses a React Native mobile-first approach and considers a Node.js/Express backend with Firebase services, MongoDB, and Redis as part of its technical architecture.

The current reported deliverables include an interactive Figma prototype and AI demonstrations for an educational chatbot and image-based skin-concern assistance. The remaining modules and integrations must be assessed against the team's implementation and testing evidence before being described as complete.

## 3. Problem statement

Pet owners may need to use different channels to keep pet information, find services, explore supplies, and seek general care guidance. A unified mobile experience could reduce the friction of switching between separate sources. At the same time, AI-assisted information must be presented responsibly and must not be mistaken for professional veterinary diagnosis.

## 4. Aim

To design and incrementally develop a mobile-first pet-care management experience that organizes pet-related information and services in one application.

## 5. Objectives

- Design a clear mobile user experience for pet-care tasks.
- Provide a concept for pet profiles and care records.
- Define service-discovery and e-commerce modules.
- Demonstrate educational conversational AI.
- Demonstrate image-based educational assistance for visible skin concerns.
- Document a maintainable full-stack architecture.
- Consider privacy, authentication, and safe AI messaging from the beginning.

## 6. Scope

### In scope

- React Native mobile application design.
- Pet profile and care-management concepts.
- Veterinary, grooming, caretaking, and related service concepts.
- Pet-related product browsing concept.
- Educational chatbot demonstration.
- Image selection/upload flow for the image-analysis demonstration.
- Technical documentation and future implementation plan.

### Out of scope for this public repository

- Application source code.
- Credentials, secrets, and private configuration.
- Claims that every module is deployed or production-ready.
- Veterinary diagnosis or treatment recommendations by AI.
- Production security certification or clinical validation.

## 7. Intended users

- Pet owners who want to organize basic pet information.
- Users looking for pet-related services.
- Users browsing pet supplies.
- Users who want general educational information about pet care.

## 8. Proposed user experience

The user opens the app, authenticates if the relevant flow is implemented, and reaches the home dashboard. From there, the design may provide access to pet information, shopping, services, AI chat, image-based assistance, and profile settings. The exact navigation and visual styling should be taken from the team's original Figma prototype: [https://www.figma.com/design/QgoD3lbqxBHkdl1xyIPDfH/Pet360?node-id=3197-2570&t=lgG1XjkUdjsz1Miz-0](https://www.figma.com/design/QgoD3lbqxBHkdl1xyIPDfH/Pet360?node-id=3197-2570&t=lgG1XjkUdjsz1Miz-0).

## 9. Technology overview

| Layer | Technology | Intended responsibility |
|---|---|---|
| Mobile | React Native | Cross-platform mobile UI |
| API | Node.js / Express | Business logic and API endpoints |
| Authentication / cloud services | Firebase | Authentication and selected Firebase services, as implemented |
| Primary document database | MongoDB | Structured application records, if used by the implementation |
| Cache | Redis | Caching / short-lived data, if required |
| AI demos | Chat and image-analysis services | Educational support demonstrations |

This is an architectural overview, not a statement that all services have already been integrated.

## 10. AI responsibility and limitations

The chatbot and image-analysis features are educational demonstrations only. They may be inaccurate and must not be presented as veterinary diagnosis. Users should be advised to consult a veterinarian for health concerns. Image outputs can be affected by lighting, image quality, angle, and other limitations.

## 11. Expected outcomes

- A documented mobile app concept and prototype.
- A clear architecture and module boundary proposal.
- A documented data model and API design proposal.
- A defined plan for validation, privacy, and future development.
- A public portfolio repository that explains the project without disclosing its source code.

## 12. Current status

Reported ready:
- Interactive Figma prototype.
- AI educational chatbot demonstration.
- AI skin/image analysis demonstration using gallery/file selection.

Not assumed complete:
- Production backend integration.
- Production authentication and authorization.
- Complete shopping, booking, and payment workflows.
- Full database integration and migrations.
- Production deployment, monitoring, and security review.
- Comprehensive usability, accessibility, and performance testing.

Update this section only when the team has verified the corresponding work.

## 13. Conclusion

Pet360 explores how a mobile application can bring pet-related information and services into one experience while using AI carefully. The next steps are to validate each module, finish integrations, test real workflows, and maintain clear boundaries between educational AI support and professional veterinary care.

## 14. Team

- Seeman Ali
- Sami Ullah
- Malik Moiz Ahmad Awan — Lead Frontend Developer & Technical Documentation Specialist

**Supervisor:** Dr Umar Shoaib
