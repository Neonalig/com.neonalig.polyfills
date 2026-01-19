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
}
```

## Installation

```json
{
  "dependencies": {
    "com.neonalig.polyfills": "1.0.0"
  }
}
```
