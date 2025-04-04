# How to Create a New MFE (Micro Frontend) 🧱

**This guide walks you through the process of creating and integrating a new Micro Frontend (MFE) into your project.**

## 🔄 Pre-checks & Global Setup

### 1. Clean Cache 🧹

Clear any cached data which might cause conflicts and verify the cache integrity.

```bash
npm cache clean --force
```

```bash
npm cache verify
```

### 2. Check Existing Global Links 🔗

List globally linked packages to check existing links.

```bash
npm ls --link --global
```

### 3. Link Automation Package ⚙️

Link your automation package globally, ensuring it's available for use.

```bash
sudo npm link automation
```

```bash
npm link automation --force
```

### 4. Verify the Link 🔍

Recheck globally linked packages to ensure the automation package is linked correctly.

```bash
npm ls --link --global
```

## 🛠️ 1. Create New MFE

Generate the new MFE using automation tools with a specified name and port.

```bash
nx g automation:mfe --name=coe-alert --port=4207
```

Then update the following manually:

- 🧭 Update all `tsconfig.json` files (add new path)
- 🚏 Add a new route in `app.routes.ts`
- 📦 Update `package.json` (generate new API script)

## 📁 2. Add New Submodule

Integrate a Git submodule for shared components or APIs.

```bash
git submodule add ssh nmcc-apis/folderName
```

Example:

```bash
git submodule add ssh://git@lht.app.lufthansa.com:7999/mcc/nmcc-alerting-api.git nmcc-apis/nmcc-alerting-api
```

Then: ✏️ Add to `.gitignore` → OpenAPI-generated files for the new MFE

To initialize or update submodules:

```bash
git submodule update --init --recursive
```

## ⚙️ 3. Configure New Base Paths

Ensure correct resource loading and routing by updating configuration files:

- ➕ Add new base path in `config.json`
- ➕ Add new base path in `app-config.service.ts`
- 🧩 Update `shared.module.ts` with `ApiConfiguration`

## ✅ 4. Final Integration

- 🧪 Add a test button in both **QA** and **DEV** environments.
- 🔁 Use it to confirm requests are handled properly by the new MFE service.

---

You're all set! 🚀
