---
ms.openlocfilehash: 0be59258df10aa13920551f011d68bc8efe20b93
ms.sourcegitcommit: 2b3b2d684259463ddfc76ad680e5e09fdc1984d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2020
ms.locfileid: "80888149"
---
### <a name="duplicated-apis-removed-from-windows-forms"></a><span data-ttu-id="16bc4-101">API duplicadas quitadas de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="16bc4-101">Duplicated APIs removed from Windows Forms</span></span>

<span data-ttu-id="16bc4-102">En .NET Core 3.0 RC1 se han quitado una serie de API que se habían duplicado accidentalmente en el espacio de nombres <xref:System.Windows.Forms?displayProperty=fullName> a partir de la versión preliminar 4 de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="16bc4-102">A number of APIs accidentally duplicated in the <xref:System.Windows.Forms?displayProperty=fullName> namespace starting in .NET Core 3.0 Preview 4 have been removed in .NET Core 3.0 RC1.</span></span>

#### <a name="change-description"></a><span data-ttu-id="16bc4-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="16bc4-103">Change description</span></span>

<span data-ttu-id="16bc4-104">La versión preliminar 4 de .NET Core 3.0 duplicó accidentalmente varios tipos en el espacio de nombres <xref:System.Windows.Forms?displayProperty=fullName> que ya existían en el espacio de nombres <xref:System.ComponentModel.Design?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="16bc4-104">.NET Core 3.0 Preview 4 inadvertently duplicated a number of types in the <xref:System.Windows.Forms?displayProperty=fullName> namespace that already existed in the <xref:System.ComponentModel.Design?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="16bc4-105">A partir de .NET Core 3.0 RC1, estos tipos duplicados ya no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="16bc4-105">Starting with .NET Core 3.0 RC1, these duplicated types are no longer available.</span></span> <span data-ttu-id="16bc4-106">En la tabla siguiente se muestran las listas del tipo original y su tipo duplicado:</span><span class="sxs-lookup"><span data-stu-id="16bc4-106">The following table shows lists the original type and its duplicated type:</span></span>

> [!div class="mx-tdCol2BreakAll"]
> |<span data-ttu-id="16bc4-107">Tipo original</span><span class="sxs-lookup"><span data-stu-id="16bc4-107">Original type</span></span>|<span data-ttu-id="16bc4-108">Tipo duplicado</span><span class="sxs-lookup"><span data-stu-id="16bc4-108">Duplicated type</span></span>|
> |---|---|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedEventArgs?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventArgs`|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedEventHandler?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventHandler`|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedType?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedType`|
> |<xref:System.ComponentModel.Design.DesignerActionUIService?displayProperty=fullName>|`System.Windows.Forms.DesignerActionUIService`|
> |<xref:System.ComponentModel.Design.DesignerCommandSet?displayProperty=fullName>|`System.Windows.Forms.DesignerCommandSet`|

#### <a name="version-introduced"></a><span data-ttu-id="16bc4-109">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="16bc4-109">Version introduced</span></span>

<span data-ttu-id="16bc4-110">3.0 RC1</span><span class="sxs-lookup"><span data-stu-id="16bc4-110">3.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="16bc4-111">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="16bc4-111">Recommended action</span></span>

<span data-ttu-id="16bc4-112">Actualice el código para hacer referencia al tipo original, como se muestra en la columna **Tipo original** de la tabla.</span><span class="sxs-lookup"><span data-stu-id="16bc4-112">Update the code to reference the original type, as shown in the **Original type** column of the table.</span></span>

#### <a name="category"></a><span data-ttu-id="16bc4-113">Categoría</span><span class="sxs-lookup"><span data-stu-id="16bc4-113">Category</span></span>

<span data-ttu-id="16bc4-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="16bc4-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="16bc4-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="16bc4-115">Affected APIs</span></span>

- <span data-ttu-id="16bc4-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="16bc4-116">None.</span></span>

<!--

### Affected APIs

- Not detectable via API analysis.

-->
