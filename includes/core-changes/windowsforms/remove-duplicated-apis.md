---
ms.openlocfilehash: 4d67da34cf692133df95480a7f0215943337a34e
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003001"
---
### <a name="duplicated-apis-removed-from-windows-forms"></a><span data-ttu-id="ffb9b-101">API duplicadas quitadas de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ffb9b-101">Duplicated APIs removed from Windows Forms</span></span>

<span data-ttu-id="ffb9b-102">En .NET Core 3.0 RC1 se han quitado una serie de API que se habían duplicado accidentalmente en el espacio de nombres <xref:System.Windows.Forms?displayProperty=fullName> a partir de la versión preliminar 4 de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="ffb9b-102">A number of APIs accidentally duplicated in the <xref:System.Windows.Forms?displayProperty=fullName> namespace starting in .NET Core 3.0 Preview 4 have been removed in .NET Core 3.0 RC1.</span></span> 

#### <a name="change-description"></a><span data-ttu-id="ffb9b-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="ffb9b-103">Change description</span></span>

<span data-ttu-id="ffb9b-104">La versión preliminar 4 de .NET Core 3.0 duplicó accidentalmente varios tipos en el espacio de nombres <xref:System.Windows.Forms?displayProperty=fullName> que ya existían en el espacio de nombres <xref:System.ComponentModel.Design?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="ffb9b-104">.NET Core 3.0 Preview 4 inadvertently duplicated a number of types in the <xref:System.Windows.Forms?displayProperty=fullName> namespace that already existed in the <xref:System.ComponentModel.Design?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="ffb9b-105">A partir de .NET Core 3.0 RC1, estos tipos duplicados ya no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="ffb9b-105">Starting with .NET Core 3.0 RC1, these duplicated types are no longer available.</span></span> <span data-ttu-id="ffb9b-106">En la tabla siguiente se muestran las listas del tipo original y su tipo duplicado:</span><span class="sxs-lookup"><span data-stu-id="ffb9b-106">The following table shows lists the original type and its duplicated type:</span></span>

|<span data-ttu-id="ffb9b-107">Tipo original</span><span class="sxs-lookup"><span data-stu-id="ffb9b-107">Original type</span></span>|<span data-ttu-id="ffb9b-108">Tipo duplicado</span><span class="sxs-lookup"><span data-stu-id="ffb9b-108">Duplicated type</span></span>|
|---|---|
|<xref:System.ComponentModel.Design.DesignerActionListsChangedEventArgs?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventArgs`|
|<xref:System.ComponentModel.Design.DesignerActionListsChangedEventHandler?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventHandler`|
|<xref:System.ComponentModel.Design.DesignerActionListsChangedType?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedType`|
|<xref:System.ComponentModel.Design.DesignerActionUIService?displayProperty=fullName>|`System.Windows.Forms.DesignerActionUIService`|
|<xref:System.ComponentModel.Design.DesignerCommandSet?displayProperty=fullName>|`System.Windows.Forms.DesignerCommandSet`|

#### <a name="version-introduced"></a><span data-ttu-id="ffb9b-109">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="ffb9b-109">Version introduced</span></span>

<span data-ttu-id="ffb9b-110">3.0 RC1</span><span class="sxs-lookup"><span data-stu-id="ffb9b-110">3.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ffb9b-111">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="ffb9b-111">Recommended action</span></span>

<span data-ttu-id="ffb9b-112">Actualice el código para hacer referencia al tipo original, como se muestra en la columna **Tipo original** de la tabla.</span><span class="sxs-lookup"><span data-stu-id="ffb9b-112">Update the code to reference the original type, as shown in the **Original type** column of the table.</span></span>

#### <a name="category"></a><span data-ttu-id="ffb9b-113">Categoría</span><span class="sxs-lookup"><span data-stu-id="ffb9b-113">Category</span></span>

<span data-ttu-id="ffb9b-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ffb9b-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ffb9b-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="ffb9b-115">Affected APIs</span></span>

- <span data-ttu-id="ffb9b-116">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="ffb9b-116">Not detectable via API analysis.</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis.

-->
