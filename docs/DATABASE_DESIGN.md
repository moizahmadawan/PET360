# Pet360 — Proposed Database Design

> This is a conceptual schema to guide implementation. It is not a verified export of the application's actual database.

## Design principles

- Use a stable unique identifier for each record.
- Keep authentication credentials out of application collections.
- Store file metadata and secure file references rather than large binary files in ordinary documents.
- Validate ownership on every pet-specific read or write.
- Avoid collecting information that is not needed.
- Establish retention and deletion behavior before production launch.

## Proposed collections

### Users

| Field | Type | Notes |
|---|---|---|
| `_id` | ObjectId | Internal record ID |
| `firebaseUid` | String | Firebase user identifier, if Firebase Auth is used |
| `displayName` | String | Display name |
| `email` | String | Optional, depending on authentication flow |
| `phone` | String | Optional; treat as personal data |
| `role` | String | Allowlisted role |
| `createdAt` | Date | Creation timestamp |
| `updatedAt` | Date | Last update timestamp |

### Pets

| Field | Type | Notes |
|---|---|---|
| `_id` | ObjectId | Pet record ID |
| `ownerId` | ObjectId / String | Owner reference |
| `name` | String | Pet name |
| `species` | String | e.g. cat or dog |
| `breed` | String | Optional |
| `dateOfBirth` | Date | Optional |
| `weight` | Number | Include units |
| `medicalNotes` | String / Array | Minimize sensitive details |
| `createdAt` | Date | Creation timestamp |

### Services

| Field | Type | Notes |
|---|---|---|
| `_id` | ObjectId | Service ID |
| `name` | String | Listing name |
| `category` | String | Veterinary, grooming, caretaking, etc. |
| `description` | String | Listing details |
| `price` | Number | Include currency separately |
| `location` | Object | Only as needed |
| `isActive` | Boolean | Listing status |

### Orders

| Field | Type | Notes |
|---|---|---|
| `_id` | ObjectId | Order ID |
| `userId` | ObjectId / String | Owner reference |
| `items` | Array | Product ID, quantity, price snapshot |
| `total` | Number | Validated server-side |
| `status` | String | Allowlisted lifecycle state |
| `createdAt` | Date | Creation timestamp |

### Appointments

| Field | Type | Notes |
|---|---|---|
| `_id` | ObjectId | Appointment ID |
| `userId` | ObjectId / String | Owner reference |
| `petId` | ObjectId / String | Pet reference |
| `serviceId` | ObjectId / String | Service reference |
| `scheduledAt` | Date | Scheduled time |
| `status` | String | Requested, confirmed, cancelled, completed |

### AIInteractionMetadata (optional)

Prefer not to store raw prompts, images, or model outputs unless a clear purpose and consent exist. If minimal audit metadata is necessary, define retention and access rules first.

| Field | Type | Notes |
|---|---|---|
| `_id` | ObjectId | Record ID |
| `userId` | ObjectId / String | Optional user reference |
| `feature` | String | Chat or image demo |
| `createdAt` | Date | Timestamp |
| `retentionUntil` | Date | Explicit retention boundary |

## Index suggestions

- `Users.firebaseUid`: unique when present.
- `Pets.ownerId`: query pets belonging to one user.
- `Services.category`, `Services.isActive`: filter active service listings.
- `Orders.userId`, `Orders.createdAt`: user order history.
- `Appointments.userId`, `Appointments.scheduledAt`: appointment lookup.

Create indexes based on measured query patterns. Add schema validation and authorization tests before production.
