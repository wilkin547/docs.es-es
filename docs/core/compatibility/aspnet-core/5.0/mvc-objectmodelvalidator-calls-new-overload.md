---
title: 'Cambio importante: MVC: Llamada a una nueva sobrecarga de ValidationVisitor.Validate por parte de ObjectModelValidator'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado MVC: Llamada a una nueva sobrecarga de ValidationVisitor.Validate por parte de ObjectModelValidator'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: b28c357f51291a4f73889d5d413a983f79e09daf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760264"
---
# <a name="mvc-objectmodelvalidator-calls-a-new-overload-of-validationvisitorvalidate"></a>MVC: Llamada a una nueva sobrecarga de ValidationVisitor.Validate por parte de ObjectModelValidator

En ASP.NET Core 5.0, se ha agregado una sobrecarga de <xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType>. La nueva sobrecarga acepta la instancia del modelo de nivel superior que contiene propiedades:

```diff
  bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel);
+ bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container);
```

<xref:Microsoft.AspNetCore.Mvc.ModelBinding.ObjectModelValidator> invoca esta nueva sobrecarga de `ValidationVisitor` para llevar a cabo la validación. Esta nueva sobrecarga es pertinente en el caso de que su biblioteca de validaciones se integre con el sistema de validación de modelos de MVC para ASP.NET Core.

Para obtener información, vea la incidencia de GitHub [n.º 26020 (dotnet/aspnetcore)](https://github.com/dotnet/aspnetcore/issues/26020).

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="old-behavior"></a>Comportamiento anterior

`ObjectModelValidator` invoca la sobrecarga siguiente durante la validación de modelos:

```csharp
ValidationVisitor.Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel)
```

## <a name="new-behavior"></a>Comportamiento nuevo

`ObjectModelValidator` invoca la sobrecarga siguiente durante la validación de modelos:

```csharp
ValidationVisitor.Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container)
```

## <a name="reason-for-change"></a>Motivo del cambio

Este cambio se ha aplicado para admitir validadores como <xref:System.ComponentModel.DataAnnotations.CompareAttribute>, que dependen de la inspección de otras propiedades.

## <a name="recommended-action"></a>Acción recomendada

Los marcos de validación que dependen de `ObjectModelValidator` para invocar la sobrecarga existente de `ValidationVisitor` deben invalidar el nuevo método al establecer como destino .NET 5.0 o una versión posterior:

```csharp
public class MyCustomValidationVisitor : ValidationVisitor
{
+  public override bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container)
+  {
+    ...
}
```

## <a name="affected-apis"></a>API afectadas

<xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`Overload:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate`

-->
