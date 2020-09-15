---
ms.openlocfilehash: 2d0798917b639bc90bf3f78f6fb9f19d0eaf2c71
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614816"
---
### <a name="incorrect-implementation-of-memberdescriptorequals"></a><span data-ttu-id="fb7f4-101">Implementación incorrecta de MemberDescriptor.Equals</span><span class="sxs-lookup"><span data-stu-id="fb7f4-101">Incorrect implementation of MemberDescriptor.Equals</span></span>

#### <a name="details"></a><span data-ttu-id="fb7f4-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="fb7f4-102">Details</span></span>

<span data-ttu-id="fb7f4-103">En la implementación original del método <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> se comparan dos propiedades de cadena diferentes de los objetos comparados: el nombre de la categoría y la cadena de descripción.</span><span class="sxs-lookup"><span data-stu-id="fb7f4-103">The original implementation of the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> method compares two different string properties from the objects being compared: the category name and the description string.</span></span> <span data-ttu-id="fb7f4-104">La solución consiste en comparar la propiedad <xref:System.ComponentModel.MemberDescriptor.Category> del primer objeto con la propiedad <xref:System.ComponentModel.MemberDescriptor.Category> del segundo y la propiedad <xref:System.ComponentModel.MemberDescriptor.Description> del primero con la propiedad <xref:System.ComponentModel.MemberDescriptor.Description> del segundo.</span><span class="sxs-lookup"><span data-stu-id="fb7f4-104">The fix is to compare the <xref:System.ComponentModel.MemberDescriptor.Category> of the first object to the <xref:System.ComponentModel.MemberDescriptor.Category> of the second one, and the <xref:System.ComponentModel.MemberDescriptor.Description> of the first to the <xref:System.ComponentModel.MemberDescriptor.Description> of the second.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="fb7f4-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="fb7f4-105">Suggestion</span></span>

<span data-ttu-id="fb7f4-106">Si la aplicación depende de que <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> a veces devuelva `false` cuando los descriptores son equivalentes, y el destino es la versión 4.6.2 de .NET Framework o una versión posterior, tiene varias opciones:</span><span class="sxs-lookup"><span data-stu-id="fb7f4-106">If your application depends on <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> sometimes returning `false` when descriptors are equivalent, and you are targeting the .NET Framework 4.6.2 or later, you have several options:</span></span>

- <span data-ttu-id="fb7f4-107">Realizar cambios de código para comparar los campos <xref:System.ComponentModel.MemberDescriptor.Category> y <xref:System.ComponentModel.MemberDescriptor.Description> de forma manual además de llamar al método <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fb7f4-107">Make code changes to compare the <xref:System.ComponentModel.MemberDescriptor.Category> and <xref:System.ComponentModel.MemberDescriptor.Description> fields manually in addition to calling the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> method.</span></span>
- <span data-ttu-id="fb7f4-108">Excluir este cambio mediante la adición del valor siguiente al archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="fb7f4-108">Opt out of this change by adding the following value to the app.config file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true" />
</runtime>
```

<span data-ttu-id="fb7f4-109">Si la aplicación está destinada a .NET Framework 4.6.1 o una versión anterior y se ejecuta en .NET Framework 4.6.2 o una versión anterior, y quiere deshabilitar este cambio, puede establecer el modificador de compatibilidad en `false` mediante la adición del valor siguiente al archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="fb7f4-109">If your application targets .NET Framework 4.6.1 or earlier and is running on the .NET Framework 4.6.2 or later and you want this change enabled, you can set the compatibility switch to `false` by adding the following value to the app.config file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=false" />
</runtime>
```

| <span data-ttu-id="fb7f4-110">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="fb7f4-110">Name</span></span>    | <span data-ttu-id="fb7f4-111">Valor</span><span class="sxs-lookup"><span data-stu-id="fb7f4-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="fb7f4-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="fb7f4-112">Scope</span></span>   | <span data-ttu-id="fb7f4-113">Borde</span><span class="sxs-lookup"><span data-stu-id="fb7f4-113">Edge</span></span>        |
| <span data-ttu-id="fb7f4-114">Versión</span><span class="sxs-lookup"><span data-stu-id="fb7f4-114">Version</span></span> | <span data-ttu-id="fb7f4-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="fb7f4-115">4.6.2</span></span>       |
| <span data-ttu-id="fb7f4-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="fb7f4-116">Type</span></span>    | <span data-ttu-id="fb7f4-117">Redestinación</span><span class="sxs-lookup"><span data-stu-id="fb7f4-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="fb7f4-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="fb7f4-118">Affected APIs</span></span>

- <xref:System.ComponentModel.MemberDescriptor.Equals(System.Object)?displayProperty=nameWithType>
