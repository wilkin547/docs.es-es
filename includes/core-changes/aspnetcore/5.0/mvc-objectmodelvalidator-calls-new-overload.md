---
ms.openlocfilehash: 5083403a24a4a695d6970ef9c7a006796f41a86b
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609308"
---
### <a name="mvc-objectmodelvalidator-calls-a-new-overload-of-validationvisitorvalidate"></a><span data-ttu-id="1b410-101">MVC: Llamada a una nueva sobrecarga de ValidationVisitor.Validate por parte de ObjectModelValidator</span><span class="sxs-lookup"><span data-stu-id="1b410-101">MVC: ObjectModelValidator calls a new overload of ValidationVisitor.Validate</span></span>

<span data-ttu-id="1b410-102">En ASP.NET Core 5.0, se ha agregado una sobrecarga de <xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1b410-102">In ASP.NET Core 5.0, an overload of the <xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType> was added.</span></span> <span data-ttu-id="1b410-103">La nueva sobrecarga acepta la instancia del modelo de nivel superior que contiene propiedades:</span><span class="sxs-lookup"><span data-stu-id="1b410-103">The new overload accepts the top-level model instance that contains properties:</span></span>

```diff
  bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel);
+ bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container);
```

<span data-ttu-id="1b410-104"><xref:Microsoft.AspNetCore.Mvc.ModelBinding.ObjectModelValidator> invoca esta nueva sobrecarga de `ValidationVisitor` para llevar a cabo la validación.</span><span class="sxs-lookup"><span data-stu-id="1b410-104"><xref:Microsoft.AspNetCore.Mvc.ModelBinding.ObjectModelValidator> invokes this new overload of `ValidationVisitor` to perform validation.</span></span> <span data-ttu-id="1b410-105">Esta nueva sobrecarga es pertinente en el caso de que su biblioteca de validaciones se integre con el sistema de validación de modelos de MVC para ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="1b410-105">This new overload is pertinent if your validation library integrates with ASP.NET Core MVC's model validation system.</span></span>

<span data-ttu-id="1b410-106">Para obtener información, vea la incidencia de GitHub [n.º 26020 (dotnet/aspnetcore)](https://github.com/dotnet/aspnetcore/issues/26020).</span><span class="sxs-lookup"><span data-stu-id="1b410-106">For discussion, see GitHub issue [dotnet/aspnetcore#26020](https://github.com/dotnet/aspnetcore/issues/26020).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="1b410-107">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="1b410-107">Version introduced</span></span>

<span data-ttu-id="1b410-108">5.0</span><span class="sxs-lookup"><span data-stu-id="1b410-108">5.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="1b410-109">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="1b410-109">Old behavior</span></span>

<span data-ttu-id="1b410-110">`ObjectModelValidator` invoca la sobrecarga siguiente durante la validación de modelos:</span><span class="sxs-lookup"><span data-stu-id="1b410-110">`ObjectModelValidator` invokes the following overload during model validation:</span></span>

```csharp
ValidationVisitor.Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel)
```

#### <a name="new-behavior"></a><span data-ttu-id="1b410-111">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="1b410-111">New behavior</span></span>

<span data-ttu-id="1b410-112">`ObjectModelValidator` invoca la sobrecarga siguiente durante la validación de modelos:</span><span class="sxs-lookup"><span data-stu-id="1b410-112">`ObjectModelValidator` invokes the following overload during model validation:</span></span>

```csharp
ValidationVisitor.Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container)
```

#### <a name="reason-for-change"></a><span data-ttu-id="1b410-113">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="1b410-113">Reason for change</span></span>

<span data-ttu-id="1b410-114">Este cambio se ha aplicado para admitir validadores como <xref:System.ComponentModel.DataAnnotations.CompareAttribute>, que dependen de la inspección de otras propiedades.</span><span class="sxs-lookup"><span data-stu-id="1b410-114">This change was introduced to support validators, such as <xref:System.ComponentModel.DataAnnotations.CompareAttribute>, that rely on inspection of other properties.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1b410-115">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="1b410-115">Recommended action</span></span>

<span data-ttu-id="1b410-116">Los marcos de validación que dependen de `ObjectModelValidator` para invocar la sobrecarga existente de `ValidationVisitor` deben invalidar el nuevo método al establecer como destino .NET 5.0 o una versión posterior:</span><span class="sxs-lookup"><span data-stu-id="1b410-116">Validation frameworks that rely on `ObjectModelValidator` to invoke the existing overload of `ValidationVisitor` must override the new method when targeting .NET 5.0 or later:</span></span>

```csharp
public class MyCustomValidationVisitor : ValidationVisitor
{
+  public override bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container)
+  {
+    ...
}
```

#### <a name="category"></a><span data-ttu-id="1b410-117">Categoría</span><span class="sxs-lookup"><span data-stu-id="1b410-117">Category</span></span>

<span data-ttu-id="1b410-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1b410-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1b410-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="1b410-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate`

-->
