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
# <a name="mvc-objectmodelvalidator-calls-a-new-overload-of-validationvisitorvalidate"></a><span data-ttu-id="86e5d-103">MVC: Llamada a una nueva sobrecarga de ValidationVisitor.Validate por parte de ObjectModelValidator</span><span class="sxs-lookup"><span data-stu-id="86e5d-103">MVC: ObjectModelValidator calls a new overload of ValidationVisitor.Validate</span></span>

<span data-ttu-id="86e5d-104">En ASP.NET Core 5.0, se ha agregado una sobrecarga de <xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="86e5d-104">In ASP.NET Core 5.0, an overload of the <xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType> was added.</span></span> <span data-ttu-id="86e5d-105">La nueva sobrecarga acepta la instancia del modelo de nivel superior que contiene propiedades:</span><span class="sxs-lookup"><span data-stu-id="86e5d-105">The new overload accepts the top-level model instance that contains properties:</span></span>

```diff
  bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel);
+ bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container);
```

<span data-ttu-id="86e5d-106"><xref:Microsoft.AspNetCore.Mvc.ModelBinding.ObjectModelValidator> invoca esta nueva sobrecarga de `ValidationVisitor` para llevar a cabo la validación.</span><span class="sxs-lookup"><span data-stu-id="86e5d-106"><xref:Microsoft.AspNetCore.Mvc.ModelBinding.ObjectModelValidator> invokes this new overload of `ValidationVisitor` to perform validation.</span></span> <span data-ttu-id="86e5d-107">Esta nueva sobrecarga es pertinente en el caso de que su biblioteca de validaciones se integre con el sistema de validación de modelos de MVC para ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="86e5d-107">This new overload is pertinent if your validation library integrates with ASP.NET Core MVC's model validation system.</span></span>

<span data-ttu-id="86e5d-108">Para obtener información, vea la incidencia de GitHub [n.º 26020 (dotnet/aspnetcore)](https://github.com/dotnet/aspnetcore/issues/26020).</span><span class="sxs-lookup"><span data-stu-id="86e5d-108">For discussion, see GitHub issue [dotnet/aspnetcore#26020](https://github.com/dotnet/aspnetcore/issues/26020).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="86e5d-109">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="86e5d-109">Version introduced</span></span>

<span data-ttu-id="86e5d-110">5.0</span><span class="sxs-lookup"><span data-stu-id="86e5d-110">5.0</span></span>

## <a name="old-behavior"></a><span data-ttu-id="86e5d-111">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="86e5d-111">Old behavior</span></span>

<span data-ttu-id="86e5d-112">`ObjectModelValidator` invoca la sobrecarga siguiente durante la validación de modelos:</span><span class="sxs-lookup"><span data-stu-id="86e5d-112">`ObjectModelValidator` invokes the following overload during model validation:</span></span>

```csharp
ValidationVisitor.Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel)
```

## <a name="new-behavior"></a><span data-ttu-id="86e5d-113">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="86e5d-113">New behavior</span></span>

<span data-ttu-id="86e5d-114">`ObjectModelValidator` invoca la sobrecarga siguiente durante la validación de modelos:</span><span class="sxs-lookup"><span data-stu-id="86e5d-114">`ObjectModelValidator` invokes the following overload during model validation:</span></span>

```csharp
ValidationVisitor.Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container)
```

## <a name="reason-for-change"></a><span data-ttu-id="86e5d-115">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="86e5d-115">Reason for change</span></span>

<span data-ttu-id="86e5d-116">Este cambio se ha aplicado para admitir validadores como <xref:System.ComponentModel.DataAnnotations.CompareAttribute>, que dependen de la inspección de otras propiedades.</span><span class="sxs-lookup"><span data-stu-id="86e5d-116">This change was introduced to support validators, such as <xref:System.ComponentModel.DataAnnotations.CompareAttribute>, that rely on inspection of other properties.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="86e5d-117">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="86e5d-117">Recommended action</span></span>

<span data-ttu-id="86e5d-118">Los marcos de validación que dependen de `ObjectModelValidator` para invocar la sobrecarga existente de `ValidationVisitor` deben invalidar el nuevo método al establecer como destino .NET 5.0 o una versión posterior:</span><span class="sxs-lookup"><span data-stu-id="86e5d-118">Validation frameworks that rely on `ObjectModelValidator` to invoke the existing overload of `ValidationVisitor` must override the new method when targeting .NET 5.0 or later:</span></span>

```csharp
public class MyCustomValidationVisitor : ValidationVisitor
{
+  public override bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container)
+  {
+    ...
}
```

## <a name="affected-apis"></a><span data-ttu-id="86e5d-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="86e5d-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`Overload:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate`

-->
