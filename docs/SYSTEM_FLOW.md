# Pet360 — System Flow

## Main user journey

```mermaid
flowchart TD
    A([Start]) --> B[Open Pet360]
    B --> C{Authentication flow implemented?}
    C -- Yes --> D[Sign in / Create account]
    C -- No / prototype --> E[Explore prototype]
    D --> F[Home dashboard]
    E --> F
    F --> G[Pet profile and care records]
    F --> H[Services]
    F --> I[Pet shop]
    F --> J[Educational AI chat]
    F --> K[Image-based assistance demo]
    G --> L[View or update pet information]
    H --> M[Browse service details]
    I --> N[Browse product details]
    J --> O[Show educational answer + disclaimer]
    K --> P[Select image + show demo result + disclaimer]
    L --> Q([Return to dashboard])
    M --> Q
    N --> Q
    O --> Q
    P --> Q
```

## Image assistance flow

1. User opens the image-assistance screen.
2. User selects an image using the supported gallery/file picker.
3. The app validates file type and size.
4. The image is sent only to the configured analysis service if the integration is enabled.
5. The service returns an educational result or a safe error.
6. The app displays the result with a clear note that it is not a diagnosis.
7. The user is encouraged to contact a veterinarian for concerns.

## Error paths to implement

- Network unavailable.
- Authentication expired.
- Image format unsupported.
- Image too large.
- AI service timeout or rate limit.
- Empty response or malformed response.
- Permission denied.
- Backend unavailable.

## Status note

This flow describes the intended user journey. It does not imply that every step has been implemented or tested.
