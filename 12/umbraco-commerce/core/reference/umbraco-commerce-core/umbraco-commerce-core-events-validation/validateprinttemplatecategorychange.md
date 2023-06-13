---
title: ValidatePrintTemplateCategoryChange
description: API reference for ValidatePrintTemplateCategoryChange in Umbraco Commerce
---
## ValidatePrintTemplateCategoryChange

```csharp
public class ValidatePrintTemplateCategoryChange : ValidationEventBase
```

**Inheritance**

* class [ValidationEventBase](../../umbraco-commerce-common/umbraco-commerce-common-events/validationeventbase.md)

**Namespace**
* [Umbraco.Commerce.Core.Events.Validation](README.md)

### Constructors

#### ValidatePrintTemplateCategoryChange

```csharp
public ValidatePrintTemplateCategoryChange(PrintTemplateReadOnly printTemplate, 
    ChangingValue<TemplateCategory> category)
```


### Properties

#### Category

```csharp
public ChangingValue<TemplateCategory> Category { get; }
```


---

#### PrintTemplate

```csharp
public PrintTemplateReadOnly PrintTemplate { get; }
```


<!-- DO NOT EDIT: generated by xmldocmd for Umbraco.Commerce.Core.dll -->