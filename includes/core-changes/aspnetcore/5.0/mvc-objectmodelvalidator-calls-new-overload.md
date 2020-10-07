---
ms.openlocfilehash: 5083403a24a4a695d6970ef9c7a006796f41a86b
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609308"
---
### <a name="mvc-objectmodelvalidator-calls-a-new-overload-of-validationvisitorvalidate"></a>MVC: Llamada a una nueva sobrecarga de ValidationVisitor.Validate por parte de ObjectModelValidator

En ASP.NET Core 5.0, se ha agregado una sobrecarga de <xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType>. La nueva sobrecarga acepta la instancia del modelo de nivel superior que contiene propiedades:

```diff
  bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel);
+ bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container);
```

<xref:Microsoft.AspNetCore.Mvc.ModelBinding.ObjectModelValidator> invoca esta nueva sobrecarga de `ValidationVisitor` para llevar a cabo la validación. Esta nueva sobrecarga es pertinente en el caso de que su biblioteca de validaciones se integre con el sistema de validación de modelos de MVC para ASP.NET Core.

Para obtener información, vea la incidencia de GitHub [n.º 26020 (dotnet/aspnetcore)](https://github.com/dotnet/aspnetcore/issues/26020).

#### <a name="version-introduced"></a>Versión introducida

5.0

#### <a name="old-behavior"></a>Comportamiento anterior

`ObjectModelValidator` invoca la sobrecarga siguiente durante la validación de modelos:

```csharp
ValidationVisitor.Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel)
```

#### <a name="new-behavior"></a>Comportamiento nuevo

`ObjectModelValidator` invoca la sobrecarga siguiente durante la validación de modelos:

```csharp
ValidationVisitor.Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container)
```

#### <a name="reason-for-change"></a>Motivo del cambio

Este cambio se ha aplicado para admitir validadores como <xref:System.ComponentModel.DataAnnotations.CompareAttribute>, que dependen de la inspección de otras propiedades.

#### <a name="recommended-action"></a>Acción recomendada

Los marcos de validación que dependen de `ObjectModelValidator` para invocar la sobrecarga existente de `ValidationVisitor` deben invalidar el nuevo método al establecer como destino .NET 5.0 o una versión posterior:

```csharp
public class MyCustomValidationVisitor : ValidationVisitor
{
+  public override bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container)
+  {
+    ...
}
```

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

<xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate`

-->
