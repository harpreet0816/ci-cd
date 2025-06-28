- Clone the repo


- npm install
- Run postgres either locally or on the cloud (neon.tech)

```jsx
docker run  -e POSTGRES_PASSWORD=mysecretpassword -d -p 5432:5432 postgres
```

- Copy over all .env.example files to .env
- Update .env files everywhere with the right db url
- Go to `packages/db`
    - npx prisma migrate dev
    - npx prisma db seed
- Go to `apps/user-app` , run `npm run dev`
- Try logging in using phone - 1111111111 , password - alice (See `seed.ts`)

# 🚀 Build on Pull Request Workflow

This repository includes a GitHub Actions workflow that automatically builds the project when a pull request is opened against the `master` branch.

## 🔧 Workflow Overview

The GitHub Actions workflow is defined in `.github/workflows/build-on-pr.yml`.

### ✅ Trigger

The workflow is triggered **on pull requests to the `master` branch**:

```yaml
on:
  pull_request:
    branches: [master]
