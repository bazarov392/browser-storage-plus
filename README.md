# Browser Storage Plus

## Installation

```bash
yarn add browser-storage-plus
```
or
```bash
npm i browser-storage-plus
```

## Features

- 🔄 Simple API similar to standard Storage
- ⏱️ Time-to-live (TTL) functionality for keys
- 🔒 Optional key encryption
- 🔄 Works with both localStorage and sessionStorage
- 📦 Tiny size with minimal dependencies

## Usage

```typescript
import { MStorage } from "browser-storage-plus";

// Create a storage instance

const storage = new MStorage({
    storage: "local" // "local" or "session", default "local"
    encryptKeys: false // set to true to encrypt keys 
});

// Set a value
storage.set('user', "Maut");
// Set a value with TTL in seconds
storage.set('auth_token', "xyz123", 3600);

// Get a value
const user = storage.get('user'); // 'Maut'

// Check remaining TTL (in seconds)
const tokenTtl = storage.ttl('auth_token');

// Remove a value
storage.remove(['user', 'auth_token']);
```