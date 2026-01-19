# Neonalig Polyfills
 
Polyfill attributes for newer C# language features to support older Unity versions. 
 
## Features 
 
- `CallerArgumentExpressionAttribute` - Allows capturing the text of argument expressions 
- `IsExternalInit` - Required for init-only setters (C# 9.0) 
- `MemberNotNullAttribute` - Nullable reference type annotations 
- `MemberNotNullWhenAttribute` - Conditional nullable reference type annotations 
 
## Usage 
 
These polyfills are automatically available when you add the package. They allow you to use modern C# features in older Unity versions: 
 
```csharp 
public class Example 
{ 
    // Use init-only properties 
    public string Name { get; init; } 
     
    // Use nullable annotations 
    [MemberNotNull(nameof(_value))] 
    private void EnsureInitialized()
    {
        _value ??= new();
    }

    private object? _value;
}
```

## Installation

### Option 1 - Package Manager (Recommended)

1. Open **Window ▸ Package Manager**
2. Click **➕**
3. Select **Install package from Git URL…**
4. Paste:

```
https://github.com/Neonalig/com.neonalig.polyfills.git#v1.0.0
```

Supported suffixes:

* `#v1.0.0` – tag
* `#main` – branch
* `#<commit-hash>` – exact commit

> **Tip:** Using a tag or commit hash is recommended for reproducible builds.

---

### Option 2 - `manifest.json`

Add to `Packages/manifest.json`:

```json
{
  "dependencies": {
    "com.neonalig.attributes": "https://github.com/Neonalig/com.neonalig.polyfills.git#v1.0.0"
  }
}
```

---

### Option 3 - Scoped Dependency

If you are consuming this from a local package or a scoped registry, use the package name directly:

```json
{
  "dependencies": {
    "com.neonalig.polyfills": "1.0.0"
  }
}
```