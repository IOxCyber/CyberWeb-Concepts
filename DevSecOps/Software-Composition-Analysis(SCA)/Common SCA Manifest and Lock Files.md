- SCA tools use these files to build a complete inventory (Software Bill of Materials or SBOM) of both **direct** and **transitive** dependencies to check against vulnerability databases.

---

### **JavaScript/TypeScript**
* `package-lock.json`
* `yarn.lock`
* `pnpm-lock.yaml`
* `lerna.json`
* `npm-shrinkwrap.json`
* `.npmrc`

### **Python**
* `Pipfile`
* `Pipfile.lock`
* `pyproject.toml`
* `poetry.lock`
* `setup.py`
* Various other `requirements-*.txt` files

### **Java**
* `build.gradle` (and `*.gradle`)
* `build.gradle.kts`
* `gradle-wrapper.properties`
* `settings.xml` (Maven settings)
* `ivy.xml`

### **Ruby**
* `Gemfile`
* `Gemfile.lock`
* `*.gemspec`

### **Go**
* `go.mod`
* `go.sum`
* `Gopkg.lock`

### **PHP**
* `composer.json`
* `composer.lock`

### **.NET/C#**
* `*.csproj`, `*.fsproj`, `*.vbproj`
* `packages.config`
* `nuget.config`
* `project.assets.json`

### **Other Languages/Tools**
* **Rust:** `Cargo.toml`, `Cargo.lock`
* **Swift/Objective-C:** `Podfile`, `Podfile.lock`, `Package.swift`, `Package.lock` (Swift Package Manager)
* **Dart:** `pubspec.yaml`, `pub.lock`
* **C/C++:** `conanfile.txt`, `conan.lock`

## 🔑 Key Distinctions:
- It's important to understand the difference between the two main types of files SCA scans utilize:

* **Manifest Files (e.g., `package.json`, `pom.xml`):** These are where developers **declare** the direct dependencies for their project. They typically specify version ranges.
* **Lock Files (e.g., `package-lock.json`, `requirements.txt` with exact versions):** These files **pinpoint** the exact versions of *all* dependencies (direct and transitive) that were resolved and installed, ensuring reproducible builds. **Lock files are generally more accurate and preferred for SCA** because they represent the actual code that is running.
