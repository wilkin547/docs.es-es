---
ms.openlocfilehash: 5bbbf9075683b0f124e126b661b4ab85011e6c2e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "74643932"
---
### <a name="change-of-access-for-accessibleobjectruntimeidfirstitem"></a><span data-ttu-id="81e77-101">Cambio de acceso para AccessibleObject.RuntimeIDFirstItem</span><span class="sxs-lookup"><span data-stu-id="81e77-101">Change of access for AccessibleObject.RuntimeIDFirstItem</span></span>

<span data-ttu-id="81e77-102">A partir de .NET Core 3.0 RC1, la accesibilidad de `AccessibleObject.RuntimeIDFirstItem` ha cambiado de `protected` a `internal`.</span><span class="sxs-lookup"><span data-stu-id="81e77-102">Starting in .NET Core 3.0 RC1, the accessibility of `AccessibleObject.RuntimeIDFirstItem` has changed from `protected` to `internal`.</span></span>

#### <a name="change-description"></a><span data-ttu-id="81e77-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="81e77-103">Change description</span></span>

<span data-ttu-id="81e77-104">A partir de la versión preliminar 4 de .NET Core 3.0, el campo `AccessibleObject.RuntimeIDFirstItem` era `protected`.</span><span class="sxs-lookup"><span data-stu-id="81e77-104">Starting with .NET Core 3.0 Preview 4, the `AccessibleObject.RuntimeIDFirstItem` field was `protected`.</span></span> <span data-ttu-id="81e77-105">A partir de la versión 3.0 RC1 de .NET Core , ha cambiado de `protected` a `internal` para alinearse con la accesibilidad del campo en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="81e77-105">Starting with .NET Core 3.0 RC1, it has changed from `protected` to `internal` to align with the accessibility of the field in the .NET Framework.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="81e77-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="81e77-106">Version introduced</span></span>

<span data-ttu-id="81e77-107">3.0 RC1</span><span class="sxs-lookup"><span data-stu-id="81e77-107">3.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="81e77-108">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="81e77-108">Recommended action</span></span>

<span data-ttu-id="81e77-109">El cambio puede afectar al usuario si ha desarrollado una aplicación .NET Core con un tipo que se deriva de <xref:System.Windows.Forms.AccessibleObject> y tiene acceso al campo `RuntimeIDFirstItem`.</span><span class="sxs-lookup"><span data-stu-id="81e77-109">The change can affect you if you've developed a .NET Core app with a type that derives from <xref:System.Windows.Forms.AccessibleObject> and accesses the `RuntimeIDFirstItem` field.</span></span> <span data-ttu-id="81e77-110">Si es así, puede definir una constante local de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="81e77-110">If this is the case, you can define a local constant as follows:</span></span>

```csharp
const int RuntimeIDFirstItem = 0x2a;
```

#### <a name="category"></a><span data-ttu-id="81e77-111">Categoría</span><span class="sxs-lookup"><span data-stu-id="81e77-111">Category</span></span>

<span data-ttu-id="81e77-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="81e77-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="81e77-113">API afectadas</span><span class="sxs-lookup"><span data-stu-id="81e77-113">Affected APIs</span></span>

- <span data-ttu-id="81e77-114">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="81e77-114">Not detectable via API analysis.</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis.

-->
